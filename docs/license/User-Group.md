# AEM License

## Custom User/Group License Example

In the event you changed the default AEM user/group.

~~~ puppet
aem::instance { 'aem' :
  source  => '/path/to/aem-quickstart.jar',
  user    => 'vagrant',
  group   => 'vagrant',
}

aem::license { 'aem' :
  customer    => 'Customer Name',
  home        => '/opt/aem',
  license_key => 'enter-your-key-here',
  version     => '6.1.0',
  user        => 'vagrant',
  group       => 'vagrant',
}

Aem::License['aem'] ~> Aem::Service['aem']
~~~

*The Aem::Service definition created for AEM uses the aem::instance $name to ensure uniqueness, thus here the service reference is 'aem'.*
