## Guzzle 7 Effective Url Middleware

A quick solution for Guzzle 7 to get request url from the response.

### Instalation
Install via composer

```
 composer require dezento/effective-url-middleware
 ```
### Usage
```
require "vendor/autoload.php";

use Dezento\EffectiveUrlMiddleware;
use GuzzleHttp\HandlerStack;
use GuzzleHttp\Client;

$stack = HandlerStack::create();
$stack->push(EffectiveUrlMiddleware::middleware());

$client = new Client([
    'handler' => $stack
]);

$response = $client->request('GET', 'http://httpbin.org/get');

echo $response->getHeaderLine('X-GUZZLE-EFFECTIVE-URL');
```
