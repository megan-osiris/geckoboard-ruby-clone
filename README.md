# geckoboard-ruby

Welcome to your new gem! In this directory, you'll find the files you need to be able to package up your Ruby library into a gem. Put your Ruby code in the file `lib/geckoboard/ruby`. To experiment with that code, run `bin/console` for an interactive prompt.

TODO: Delete this and the text above, and describe your gem

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'geckoboard-ruby'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install geckoboard-ruby

## Usage

### Ping to authenticate

Verify that your API key is valid and that you can reach the Geckoboard API.

```ruby
client = Geckoboard.client('222efc82e7933138077b1c2554439e15')
client.ping # => true
```

### Find or create

Verify an existing dataset or create a new one.

```ruby
dataset = client.datasets.find_or_create('sales.gross', fields: {
  amount: {
    type: :number,
    name: 'Amount',
  },
  timestamp: {
    type: :datetime,
    name: 'Time'
  }
})
```

### Delete

Delete a dataset and all data therein.

```ruby
dataset.delete # => true
```

Delete a dataset with a given id.

```ruby
client.datasets.delete('sales.gross') # => true
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/geckoboard-ruby/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request