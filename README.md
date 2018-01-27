# phone-number-validator

PhoneNumber validation component for Symfony based frameworks (Symfony, Silex, Drupal etc.)

## Installation
The best way to install JSendResponse is to use a [Composer](https://getcomposer.org/download):

    php composer.phar require junker/phone-number-validator


## Examples

```php
use Junker\PhoneNumberValidator\Constraints\PhoneNumber as AssertPhoneNumber;

class AppController
{
    ...

    protected function validate($data)
    { 
        $fields = [
            'phone' => new AssertPhoneNumber([
                        'value' => $data['phone'], 
                        'message' => 'Wrong phone number',
                        'type' => "mobile", # //optional
                        'defaultRegion' => "GB", # //optional
            ])
        ];

        $constraint = new Assert\Collection([
            'fields' => $fields
        ]);

        return $app['validator']->validate($data, $constraint);
    }

    ...
}

```

Based on PhoneNumberBundle (https://github.com/misd-service-development/phone-number-bundle)
