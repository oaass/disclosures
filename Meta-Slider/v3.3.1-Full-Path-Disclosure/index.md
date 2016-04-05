# Meta Slider v3.3.1 – Full Path Disclosure  

**Discovered by:** Ole Aass  
**Discovery date:** 2015-04-16  
**Vendor:** Matcha Labs  
**Vendor url:** https://profiles.wordpress.org/matchalabs  
**Application:** Meta Slider  
**Vulnerable Version:** 3.3.1  
**Websites:**

* https://www.metaslider.com/
* https://wordpress.org/plugins/ml-slider/

## Vulnerabilities

* [Information Exposure (CWE-200)](https://cwe.mitre.org/data/definitions/200.html)

## Description

There was found 5 files which are expsing sensitive information when the server is set to display errors

* inc/slide/metaslide.image.class.php
    ```
    Fatal error: Class 'MetaSlide' not found in ****/ml-slider/inc/slide/metaslide.image.class.php on line 5
    ```

* inc/slider/metaslider.coin.class.php
    ```    
    Fatal error: Class 'MetaSlider' not found in ****/ml-slider/inc/slider/metaslider.coin.class.php on line 6
    ```

* inc/slider/metaslider.flex.class.php
    ```
    Fatal error: Class 'MetaSlider' not found in ****/ml-slider/inc/slider/metaslider.flex.class.php on line 5
    ```

* inc/slider/metaslider.nivo.class.php
    ```
    Fatal error: Class 'MetaSlider' not found in ****/ml-slider/inc/slider/metaslider.nivo.class.php on line 5
    ```

* inc/slider/metaslider.responsive.class.php
    ```
    Fatal error: Class 'MetaSlider' not found in ****/ml-slider/inc/slider/metaslider.responsive.class.php on line 5
    ```

## Solution

Update to latest version of the plugin

## Timeline

* 2015-04-16 - Contacted vendor and wordpress security team  
* 2015-04-16 - Vendor released fix