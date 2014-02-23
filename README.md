# ruby-debug-passenger

## Background
I wanted to use Phusion Passenger as an Apache module (not standalone) but still
be able to use the interactive Ruby debugger.

Thanks to
[Adam Meehan](http://duckpunching.com/passenger-mod_rails-for-development-now-with-debugger)
I was able to do that, and I decided to make it into a reusable Gem.

## Requirements

* Ruby on Rails 3.0+
* Ruby 1.9+ (untested on 1.8 but it may work)
* Ruby Debug / Debugger / Byebug
* Phusion Passenger

## Installation
Add this to your `Gemfile` if you are on Ruby 2.0:

```ruby
gem "byebug"
gem "ruby-debug-passenger"
```

Or this if you are on Ruby 1.9:

```ruby
gem "debugger"
gem "ruby-debug-passenger"
```

Or this if you are on Ruby 1.8 (but it hasn't been tested!):

```ruby
gem "ruby-debug"
gem "ruby-debug-passenger"
```

Then run `bundle install` to install it.

## Usage
Add `debugger` (Ruby 1.9 or lower) or `byebug` (Ruby 2.0+) anywhere
in your Ruby code that you want to invoke the debugger. Or in an ERB template
add `<% debugger %>` or `<% byebug %>` instead.

Run `rake debug` to restart Phusion Passenger and connect to the debugger. (You
will be prompted to reload the app in your browser.)

## Recommended reading
* [ruby-debug documentation](http://bashdb.sourceforge.net/ruby-debug.html)
* [RailsCast #54](http://railscasts.com/episodes/54-debugging-with-ruby-debug),
  or the [revised version](http://railscasts.com/episodes/54-debugging-ruby-revised)
  if you're a Pro subscriber.

## Changelog
### 0.2.0
* Support for `byebug` gem (David Rodríguez) - [#2](https://github.com/davejamesmiller/ruby-debug-passenger/pull/2)

### 0.1.0
* Support for `debugger` gem (Kai Middleton) - [#1](https://github.com/davejamesmiller/ruby-debug-passenger/pull/1)

### 0.0.1
* Initial release

## License
MIT License - see `LICENSE.txt`.
