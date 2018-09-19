# WalletStripe

Description
--------------------

php component to connect applications with stripe


Installation / Usage
--------------------


## Via Composer

``` bash
$ composer require suseche/walletstripe
```
## After installing via composer, run the migration command


``` bash
$ php artisan migrate 
```
## Create Account in Stripe 

[https://stripe.com//](https://stripe.com/)

In the dashboard options

-Developers
 -API Keys

copy the Secret key

In the laravel environment file should go the following data
	-STRIPE_KEY (Secret key from stripe)
	-APP_ENV
	-APP_NAME


Requirements
------------

- PHP 7.1.3
- Laravel 5.6



Usage
---------


``` php

namespace App\Http\Controllers;


use suseche\walletstripe\WalletStripe;

class UserController extends Controller
{
    public function createCustomer(Request $request)
    {
    	$wallet = new WalletStripe;
    	$customer = $wallet->createConstumer($user->id);
    }
}

```


Methods
---------

##createConstumer

-code 
	---------

``` php
		$wallet = new WalletStripe;
    	$customer = $wallet->createConstumer($user->id);
```

- params
	---------

	- account_id: Local identifier of the account to which you want to link the customer stripe

- return 
	---------
	- all customer data stored in stripe

##getCostumerId

-code 
	---------

``` php
		$wallet = new WalletStripe;
    	$customer = $wallet->getCostumerId($user->id);
```

- params
	---------

	- account_id: Local identifier of the account.

- return 
	---------
	- the customer identifier in stripe


##getDataCustomer
-code 
	---------

``` php
		$wallet = new WalletStripe;
    	$customer = $wallet->getDataCustomer($user->id);
```

- params
	---------

	- account_id: Local identifier of the account.

- return 
	---------
	- all customer data stored in stripe


##createCreditCard
-code 
	---------

``` php
		$wallet = new WalletStripe;
    	$customer = $wallet->createCreditCard($user->id,$token_card);
```

- params
	---------

	- account_id: Local identifier of the account.
	- $token: Token generated by the front end of stripe using the public key.

- return 
	---------
	- all credit card data stored in stripe

##getCreditCards

-code 
	---------

``` php
		$wallet = new WalletStripe;
    	$customer = $wallet->getCreditCards($user->id,$token_card);
```

- params
	---------

	- account_id: Local identifier of the account.
	- $card_id: (optional) identifier of the credit card in stripe, if the value is not sent the function returns a list of the credit cards

- return 
	---------
	- all credit card data stored in stripe / list credit cards

##deleteCreditCard
##updateCreditCard
##generateTokenCreditCard
##loadCharge



