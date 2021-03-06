![alt text](https://i.imgur.com/dep9jTz.png)



## Class to increase the performance of Mobile Detect lib.

https://github.com/leean543/Mobile-Detect

### Requires Mobile Detect
https://github.com/serbanghita/Mobile-Detect

Developed with the support of

[<img  height="30" src="https://signup.saucelabs.com/static/654e56cd1f352549040b86c70e38d345.png">](https://saucelabs.com/)


## Performance
## Up to 9 times faster.

Result of examples/test.php:

    Mobile_Detect native version detection for common UA:
    4.4974 seconds native version for common UA

    Mobile_Detect_Fast fast version detection for common UA:
    0.5429 seconds fast version for common UA

    Mobile_Detect native version detection for not mobile:
    0 fails
    Mobile_Detect native version detection for mobile:
    29 fails
    4.1812 seconds native version

    Mobile_Detect_Fast fast version detection for not mobile:
    0 fails
    Mobile_Detect_Fast fast version detection for mobile:
    28 fails
    1.7568 seconds fast version

# How
Mobile Detect uses a loop with regular expressions to determine the device, and PHP is very slow on this. By reducing the size of the string in the regular expression we get increased performance.

The information theory says that the most frequent words provide less information. Then if it appears in 100% of cases the word "Mozilla" can exclude it from the regular expression as it will be irrelevant in determining the device in the User Agent.

What we do is create an array ($irrelevant) with the list of "irrelevant words" to exclude of User Agent.

# Help
No method is overwritten, you can create an Mobile_Detect_Fast instance and continue using the native methods of the class.

Added 3 new methods: isMobileFast, isTabletFast and isPhoneFast.

    include('[PATH]/Mobile_Detect.php');
    include('[PATH]/Mobile_Detect_Fast.php');

    $detect = new LanaGuani\Mobile_Detect_Fast();
    $detect->isMobileFast(); // equivalent to $detect->isMobile();
    $detect->isTabletFast(); // equivalent to $detect->isTablet();
    $detect->isPhoneFast();  // equivalent to $detect->isMobile() && !$detect->isTablet()

# Version
Version 2.8.2-dev for 2.8.x of Mobile Detect


[<img  height="20" src="https://www.lambdatest.com/static/images/logo.svg">](https://www.lambdatest.com/)
