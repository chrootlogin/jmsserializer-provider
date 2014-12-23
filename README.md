Silex JMS Serializer Provider
=============================

A simple silex provider for the famous [JMS Serializer](http://jmsyst.com/libs/serializer).

[![Build Status](https://api.travis-ci.org/chrootlogin/jms-serializerprovider.png?branch=master)](https://travis-ci.org/chrootlogin/jms-serializerprovider)
[![Total Downloads](https://poser.pugx.org/rootlogin/jms-serializerprovider/downloads.png)](https://packagist.org/packages/rootlogin/jms-serializerprovider)
[![Latest Stable Version](https://poser.pugx.org/rootlogin/jms-serializerprovider/v/stable.png)](https://packagist.org/packages/rootlogin/jms-serializerprovider)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/chrootlogin/jms-serializerprovider/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/chrootlogin/jms-serializerprovider/?branch=master)

Installation
------------

Add the provider to your composer.json
``` {.json}
{
  "requires": {
    "rootlogin/jms-serializerprovider": "dev-master"
  }
}
```

Register the provider in your silex application:
``` {.php}
$app->register(new rootLogin\JMSSerializerProvider\JMSSerializerProvider(), array(
  "jmsserializer.cache_dir" => null,
  "jmsserializer.debug" => false,
  "jmsserializer.metadata_dir" => null
));
```

Then you can use the JMS Serializer in your controllers like this:
``` {.php}
$controllers->get("/serialize", function() use ($app, $object) {
  return new JSONResponse($app['jmsserializer']->serialize($object, 'json'));
});
```

Please refer to the [manual of JMS Serializer](http://jmsyst.com/libs/serializer) if you need more information how to use it.

Run the tests
-------------
Go to the base directory of the jms-serializerprovider. Do a `composer install` and enter `vendor/bin/phpunit`.


Contribution
------------
Pull request are welcome. Or if you can't or want code you can also contribute by opening a ticket if you see something is wrong.

Warning
-------
This project is in early development stages. No warranty if it kills your kittens or starts a nuclear war ;)
