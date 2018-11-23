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

To install with composer run the following command `composer require davmixcool/coinpayments` and then include the following line in your project where you want to use the wrapper's classes.

```php
require_once('your_project_path_to/vendor/autoload.php');
``` 

### Usage
The simplest example is retrieving basic account information. 

```php
use Davmixcool\CoinpaymentApi;

/** Scenario: Retrieve basic user account information.**/
// Either include the sample keys.php file (once populated) or manually set $public_key and $private_key variables
require('/your_installation_path_to/src/keys.php');

// Create a new API wrapper instance and call to the get basic account information command.
try {
    $cps_api = new CoinPayments($private_key, $public_key, 'json');
    $information = $cps_api->GetBasicInfo();
} catch (Exception $e) {
    echo 'Error: ' . $e->getMessage();
    exit();
}

// Check for success of API call
if ($cps_api['error'] == 'ok') {
    // Prepare start of sample HTML output
    $output = '<table><tbody><tr><td>Username</td><td>Merchant ID</td><td>Email</td><td>Public Name</td></tr>';
    $output .= '<tr><td>' . $cps_api['result']['username'] . '</td><td>' . $cps_api['result']['merchant_id'] . '</td><td>' . $cps_api['result']['email'] . '</td><td>' . $cps_api['result']['public_name'] . '</td></tr>';
    // Close the sample output HTML and echo it onto the page
    $output .= '</tbody></table>';
    echo $output;
} else {
    // Throw an error if both API calls were not successful
    echo 'There was an error returned by the API call: ' . $balances['error'] . '<br>Rates API call status: ' . $rates['error'];
}
```

### Maintainers

This package is maintained by [David Oti](http://github.com/davmixcool) and you!


### License

This package is licensed under the [MIT license](https://github.com/davmixcool/coin-payments/blob/master/LICENSE).
