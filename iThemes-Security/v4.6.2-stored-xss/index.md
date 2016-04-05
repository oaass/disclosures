# iThemes Security v4.6.12 Stored XSS

**Discovered by:** Ole Aass  
**Discovery date:** 2015-03-23  
**Vendor:** iThemes  
**Vendor url:** https://ithemes.com/  
**Application:** iThemes Security  
**Vulnerable Version:** 3.0.0 – 4.6.12 
**Websites:**

* https://ithemes.com/security/
* https://wordpress.org/plugins/better-wp-security/

## Vulnerabilities

* [Cross-Site Scripting (CWE-79)](https://cwe.mitre.org/data/definitions/79.html)

## Description

If the plugin has been configured to log 404’s, this plugin is prone to stored cross-site scripting through the referer.

The vulnerable code can be found in ‘better-wp-security/modules/free/four-oh-four/class-itsec-four-oh-four.php’ on line 40 to 51

```php
$itsec_logger->log_event(
    'four_oh_four',
    3,
    array(
        'query_string' => isset( $uri[1] ) ? esc_sql( $uri[1] ) : '', <== Vulnerable line
    ),
    ITSEC_Lib::get_ip(),
    '',
    '',
    esc_sql( $uri[0] ),
    isset( $_SERVER['HTTP_REFERER'] ) ? esc_sql( $_SERVER['HTTP_REFERER'] ) : '' <== Vulnerable line
);
```

Additional note: After reporting it also became clear that also the query string was vulnerable to the same attack as the referer header. This was patched along with the originally reported vulnerability

## Solution

Update to latest version released by vendor

## Timeline

* 2015-03-23 - Contacted vendor
* 2015-04-11 - New attempt to contact vendor through different channel
* 2015-04-12 - An iThemes developer replied on Twitter with invalid email address
* 2015-04-12 - Got hold of a person working with iThemes and reported the issue
* 2015-04-14 - Vendor released patched version