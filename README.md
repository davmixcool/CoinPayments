# CoinPayments.net PHP API Wrapper.

A PHP wrapper for CoinPayments.net Api. For account instructions visit: [online API documentation](https://www.coinpayments.net/apidoc-intro) to learn how to setup your API Keys and get a link to your account API Keys page.


## Requirements

- PHP 5.5 and above

## Steps:

* [Installation](#installation)
* [Usage](#usage)
* [Example](#example)
* [Maintainers](#maintainers)
* [License](#license)


### Installation

**Composer**

Run the following command to include this package via Composer

```shell
composer require davmixcool/coinpayments
```


### Usage
The simplest example is retrieving basic account information. 

```php
use Davmixcool\CoinPayments;

/** Scenario: Retrieve basic user account information.**/

try {
    $cps_api = new CoinPayments($private_key, $public_key, 'json');
    $information = $cps_api->GetBasicInfo();
} catch (Exception $e) {
    echo 'Error: ' . $e->getMessage();
    exit();
}

// Check for success of API call
if ($cps_api['error'] == 'ok') {
    // Prepare output

} else {
    // Throw an error if both API calls were not successful

}
```
See examples [here](https://github.com/davmixcool/CoinPayments/tree/master/example). for detailed scenarios.

### Maintainers

This package is maintained by [David Oti](http://github.com/davmixcool) and you!


### License

This package is licensed under the [MIT license](https://github.com/davmixcool/coin-payments/blob/master/LICENSE).
