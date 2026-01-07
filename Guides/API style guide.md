In this style guide, we have put together a list of best practices for API development.

# Documentation

Each new or updated API endpoint must come with documentation, unless it is internal or behind a feature flag.

# Methods and parameters description

Every method must be described using the :

- `desc` for the method summary.
- `params` for the method parameters.

A good example is as follows:

```ruby
desc 'Get all broadcast messages' do
  detail 'This feature was introduced in GitLab 8.12.'
  success Entities::BroadcastMessage
end
params do
  optional :page,     type: Integer, desc: 'Current page number'
  optional :per_page, type: Integer, desc: 'Number of messages per page'
end
get do
  messages = BroadcastMessage.all

  present paginate(messages), with: Entities::BroadcastMessage
end
```

# Array types

...

\


\
