# squirtle
Generate your API documention based on your RSpec

### What's Squirtle ?
Squirtle is an attempt to generate API documentation based on your RSpec test suite.

### Why ?
I'm currently working on a large API, and it tooks me a huge amount of time to maintain the API document (thanks to [Slate](https://github.com/tripit/slate)).

Every time I update a `strong_parameters`, add a new column on a response, I've to update the associate document. 

It goes even worse when I'm adding a new column on a `Model`: I've to go through my whole API and manually add this new field on each response.

I'm a developper, I'm lazy: I don't like this

### What do I need to create a survivable API documentation ?
1. Verb (`GET` / `POST` / ...)
2. Status Code (`200 - OK`, `201 - Created`, ...)
3. Endpoint (`/api/v1/my_module/my_controller/action`)
4. Endpoint Response (success and error)
5. Endpoint Request Parameters

### How to use it ?
Simply add `squirtle: {}` on one of your test.

Example:

```ruby
it 'does something', squirtle: {} do
  # your test
end
```

### How does it work ?
It uses RSpec hook `config.after(:each)` to extract useful information from your test.

This hook is really nice, because you have access to variables that will help you generate your doc:
- `test`: the parameter yielded by the hook
- `@request`: the request made against your controller
- `@response`: the response send by controller (including status, parameters etc...)


#### What can we get from `request` ?

#### What can we get from `response` ?

#### What can we get from `test` ?

