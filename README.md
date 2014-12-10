# Logging::Logstash

This is a Logstash appender for the Logging framework.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'logging-logstash'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install logging-logstash

## Usage

Configure it as an appender:

Logging.add_appender(Logging::Appenders.logtash('mylog',:uri => 'tcp:loghost:5229')

then log hashes or strings:

    Logging.root.info("string")

String messages will be logged like a {:message => message} hash.

    Logging.root.info(:my => "string", :app => "myappname")

The given hash will be enhanced by the following keys:
 * @timestamp
 * @version
 * severity (uppercase name of log level)
 * host (host of the logger)
 * everything from the mdc (Mapped Diagnostic Context) hash

## Contributing

1. Fork it ( https://github.com/[my-github-username]/logging-logstash/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
