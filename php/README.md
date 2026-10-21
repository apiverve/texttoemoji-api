# Text to Emoji API - PHP Package

Text to Emoji converts plain text strings into matching emoji representations. Send any word or phrase and receive the corresponding emoji characters.

## Installation

Install via Composer:

```bash
composer require apiverve/texttoemoji
```

## Getting Started

Get your API key at [APIVerve](https://apiverve.com)

### Basic Usage

```php
<?php

require_once 'vendor/autoload.php';

use APIVerve\Texttoemoji\Client;

// Initialize the client
$client = new Client('YOUR_API_KEY');

// Make a request
$response = $client->execute(['text' => 'I am so excited to go to the lake and swim']);

// Print the response
print_r($response);
```


### Error Handling

```php
use APIVerve\Texttoemoji\Client;
use APIVerve\Texttoemoji\Exceptions\APIException;
use APIVerve\Texttoemoji\Exceptions\ValidationException;

try {
    $response = $client->execute(['text' => 'I am so excited to go to the lake and swim']);
    print_r($response['data']);
} catch (ValidationException $e) {
    echo "Validation error: " . implode(', ', $e->getErrors());
} catch (APIException $e) {
    echo "API error: " . $e->getMessage();
    echo "Status code: " . $e->getStatusCode();
}
```

### Debug Mode

```php
// Enable debug logging
$client = new Client(
    apiKey: 'YOUR_API_KEY',
    debug: true
);
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

## Requirements

- PHP 7.4 or higher
- Guzzle HTTP client

## Documentation

For more information, visit the [API Documentation](https://docs.apiverve.com/ref/texttoemoji?utm_source=packagist&utm_medium=referral&utm_content=readme).

## Support

- Website: [https://apiverve.com/marketplace/texttoemoji?utm_source=php&utm_medium=referral&utm_content=readme](https://apiverve.com/marketplace/texttoemoji?utm_source=php&utm_medium=referral&utm_content=readme)
- Email: hello@apiverve.com

## License

This package is available under the [MIT License](LICENSE).
