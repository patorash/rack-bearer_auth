# Rack::BearerAuth

Rack::BearerAuth is middleware that make using [RFC 6750](https://tools.ietf.org/html/rfc6750) bearer auth in Rack apps.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'rack-bearer_auth'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install rack-bearer_auth

## Configuration

### Rsils configuration

``` ruby
module YourApp
  class Application < Rails::Application

    # ...

    config.middleware.use, Rack::AuthBearer do
      match path: "/foo" do |token|
        # validate token
      end

      match via: :all do |token|
        # validate token
      end
    end
  end
end
```

### Rack configuration

``` ruby
use Rack::BearerAuth do
  match path: "/foo" do |token|
    # validate token
  end

  match via: :all do |token|
    # validate token
  end
end

```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/yujideveloper/rack-bearer_auth.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
