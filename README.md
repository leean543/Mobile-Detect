# Mobile Detect
### The lightweight PHP class for detecting mobile devices.

Mobile\_Detect is a lightweight PHP class for detecting mobile devices. It uses the user-agent string combined with specific HTTP headers to detect the mobile environment.

**Note:** this project is _the same_ with [http://code.google.com/p/php-mobile-detect/](http://code.google.com/p/php-mobile-detect/). We are keeping both repositories updated until the transition to GitHub is completed.

Sponsored by ![BrowserStack](http://jquery.org/wp-content/uploads/2010/01/browserstack-150.png).
[BrowserStack](http://www.browserstack.com) is a complete browser coverage tool (including mobile devices) for testing you web application.

### Usage

Include and instantiate the class:
```
<?php
include 'Mobile_Detect.php';
$detect = new Mobile_Detect();
```
Basic usage, looking for mobile devices or tablets:
```
<?php
if ($detect->isMobile()) {
    // Any mobile device.
}
```

```
<?php
if($detect->isTablet()){
    // Any tablet device.
}
```

Check for a specific platform:
```
<?php
if($detect->isiOS()){
    // Code to run for the Apple's iOS platform.
}
```

```
<?php
if($detect->isAndroidOS()){
    // Code to run for the Google's Android platform.
}
```
Other case insensitive available methods are `isIphone()`, `isIpad()`, `isBlackBerry()`, `isKindle()`, `isOpera()`, etc. For the full list of available methods check the `demo.php` file.

Alternative method `is()` for checking specific properties (in beta):
```
<?php
$detect->is('Chrome')
$detect->is('iOS')
$detect->is('UC Browser')
[...]
```

Batch mode using `setUserAgent()`:
```
<?php
$userAgents = array(
'Mozilla/5.0 (Linux; Android 4.0.4; Desire HD Build/IMM76D) AppleWebKit/535.19 (KHTML, like Gecko) Chrome/18.0.1025.166 Mobile Safari/535.19',
'BlackBerry7100i/4.1.0 Profile/MIDP-2.0 Configuration/CLDC-1.1 VendorID/103',
[...]
);
foreach($userAgents as $userAgent){
  $detect->setUserAgent($userAgent);
  $isMobile = $detect->isMobile();
  $isTablet = $detect->isTablet();
  // Use the force however you want.
}
```

Get the `version()` of components (in beta):
```
<?php
$detect->version('iPad'); // 4.3 (float)
$detect->version('iPhone') // 3.1 (float)
$detect->version('Android'); // 2.1 (float)
$detect->version('Opera Mini'); // 5.0 (float)
[...]
```

### Projects based on the class

* **Symphony2** bundle for detecting mobile devices - [https://github.com/suncat2000/MobileDetectBundle](https://github.com/suncat2000/MobileDetectBundle)
* **Drupal Context Mobile Detect module** - [http://drupal.org/project/context_mobile_detect](http://drupal.org/project/context_mobile_detect)
* **Wordpress WP Mobile Detect module** - [http://wordpress.org/extend/plugins/wp-mobile-detect/](http://wordpress.org/extend/plugins/wp-mobile-detect/)