[![Dependency Status](https://gemnasium.com/rikas/slack-poster.svg)](https://gemnasium.com/rikas/slack-poster)

# Slack Poster

[Slack](https://slack.com/) is a mashup of chatrooms and collaborative sharing tools that are meant to do away with redundant conversations in multiple places.

slack-poster is a simple gem to make your integration with Slack easier. It supports only incoming communications (from you to Slack).

## Installation

Add this line to your application's Gemfile:

```console
$ gem 'slack-poster'
```

And then execute:

```console
$ bundle
```

Or install it yourself as:

```console
$ gem install slack-poster
```

## Usage

First, you need to create an Incoming Webhook integration at https://team-name.slack.com/services/new/incoming-webhook and take note of the generated token.

Next, create a new poster and send the message:

```ruby
TEAM = 'team-name'
TOKEN = 'hd7heoo2oijd0'

poster = Slack::Poster.new(TEAM, TOKEN)
poster.send_message('Hello, world!')
```

You can use an options array if you don't want to use the settings configured directly on Slack:

```ruby
options = {
  icon_url: 'http://example.com/image.png',
  # or icon_emoji: 'emoji_name',
  username: 'Tester',
  channel: '#random'
}
```

And then use it as a third parameter. Note that every option is optional (no pun intended!).

```ruby
poster = Slack::Poster.new(TEAM, TOKEN, options)
poster.send_message('Hi!') # will send to #random with the username 'Tester'
```

That's it!

## Contributing

1. Fork it ( http://github.com/rikas/slack-poster/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
