# Text to Emoji API - Ruby Gem

Text to Emoji converts plain text strings into matching emoji representations. Send any word or phrase and receive the corresponding emoji characters.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'apiverve_texttoemoji'
```

And then execute:

```bash
$ bundle install
```

Or install it yourself as:

```bash
$ gem install apiverve_texttoemoji
```

## Getting Started

Get your API key at [APIVerve](https://apiverve.com)

### Basic Usage

```ruby
require 'apiverve_texttoemoji'

# Initialize the client
client = APIVerve::Texttoemoji::Client.new(api_key: "YOUR_API_KEY")

# Make a request
response = client.execute({ text: "I am so excited to go to the lake and swim" })

# Print the response
puts response
```


### Error Handling

```ruby
begin
  response = client.execute({ text: "I am so excited to go to the lake and swim" })
  puts response["data"]
rescue APIVerve::Texttoemoji::ValidationError => e
  puts "Validation error: #{e.errors.join(', ')}"
rescue APIVerve::Texttoemoji::APIError => e
  puts "API error: #{e.message}"
  puts "Status code: #{e.status_code}"
end
```

### Debug Mode

```ruby
# Enable debug logging
client = APIVerve::Texttoemoji::Client.new(
  api_key: "YOUR_API_KEY",
  debug: true
)
```

## Example Response

```json
{
  "status": "ok",
  "error": null,
  "data": {
    "emojis": [
      "👈🏾",
      "✨👏",
      "🔥👏🏽",
      "👊🏾💪🏾",
      "🔥🤙🏼",
      "🤌🏽🔥",
      "🤩👏🏻",
      "😁📚🙌",
      "😞",
      "👉🏽👈🏽"
    ]
  }
}
```

## Documentation

For more information, visit the [API Documentation](https://docs.apiverve.com/ref/texttoemoji?utm_source=rubygems&utm_medium=referral&utm_content=readme).

## Support

- Website: [https://apiverve.com/marketplace/texttoemoji?utm_source=ruby&utm_medium=referral&utm_content=readme](https://apiverve.com/marketplace/texttoemoji?utm_source=ruby&utm_medium=referral&utm_content=readme)
- Email: hello@apiverve.com

## License

This gem is available under the [MIT License](LICENSE).
