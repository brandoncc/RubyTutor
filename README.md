# RubyTutor

RubyTutor is an irb tool to help new developers and developers new to using Ruby on the fundamentals of the language.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'rubytutor'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install rubytutor

## Usage

RubyTutor has 4 class methods that can be useful to developers:

* `RubyTutor.explain_full(object)`
* `RubyTutor.explain(object)`
* `RubyTutor.describe(object)`
* `RubyTutor.available_methods(object, filter)`

`explain_full` outputs a list of attributes pertaining to the object passed in.

Here is a sample output:

```ruby
RubyTutor.explain_full 'string'

# >> Instance of Class: String
# >> Value: stringLength: 6
# >> Mutable? Yes
# >> Object ID: 70179170680460
# >> Inhertits From: Comparable, Object, Kernel, BasicObject
# >>
# >> Description:
# >> This object is an instance of the String class.
# >> A String object is an expression that can hold
# >> letters, numbers and all sorts of different characters,
# >> as long as they are surrounded by single ('')
# >> or double ("") quotes.
# >> Type RubyTutor.available_methods String
# >> to see all of the methods available.
```

`explain` outputs the first half of `explain_full` while `describe` outputs the second half of `explain_full`.

Examples:

```ruby
RubyTutor.explain 'string'

# >> Instance of Class: String
# >> Value: stringLength: 6
# >> Mutable? Yes
# >> Object ID: 70179170680460
# >> Inhertits From: Comparable, Object, Kernel, BasicObject

RubyTutor.describe 'string'

# >> Description:
# >> This object is an instance of the String class.
# >> A String object is an expression that can hold
# >> letters, numbers and all sorts of different characters,
# >> as long as they are surrounded by single ('')
# >> or double ("") quotes.
# >> Type RubyTutor.available_methods String
# >> to see all of the methods available.
```

Lastly, `available_methods` outputs all the available methods for the object passed in. `available_methods` also has an optional filter you can pass in. The filter must be a string and the filter only corresponds to the beginning of the method name. In other words, a filter of `'to'` will return all the methods that begin with `'to'`.

Example output:

```ruby
RubyTutor.available_methods BasicObject

# >> Available Methods:
# >> !
# >> !=
# >> !~
# >> <
# >> <=
# >> <=>
# >> ==
# >> ===
# >> =~
# >> >
# >> >=
# >> __id__
# >> __send__
# >> allocate
# >> ancestors
# >> autoload
# >> autoload?
# >> class
# >> class_eval
# >> class_exec
# >> class_variable_defined?
# >> class_variable_get
# >> class_variable_set
# >> class_variables
#...(truncated for brevity)

RubyTutor.available_methods BasicObject, 'al'

# >> Available Methods:
# >> allocate
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/tutor.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
