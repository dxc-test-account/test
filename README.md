
#ZAP Scanning Report




##Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 0 |
| Low | 2 |
| Informational | 1 |

##Alert Detail


  
  
  
### Cookie No HttpOnly Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
  
  
  
* URL: [https://my.dxc.com/](https://my.dxc.com/)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
* URL: [https://my.dxc.com/sitemap.xml](https://my.dxc.com/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
* URL: [https://my.dxc.com](https://my.dxc.com)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com/robots.txt](https://my.dxc.com/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com/robots.txt](https://my.dxc.com/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
* URL: [https://my.dxc.com/sitemap.xml](https://my.dxc.com/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com/](https://my.dxc.com/)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com](https://my.dxc.com)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
Instances: 8
  
### Solution
<p>Ensure that the HttpOnly flag is set for all cookies.</p>
  
### Reference
* http://www.owasp.org/index.php/HttpOnly

  
#### CWE Id : 16
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
### Cookie Without Secure Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the secure flag, which means that the cookie can be accessed via unencrypted connections.</p>
  
  
  
* URL: [https://my.dxc.com/sitemap.xml](https://my.dxc.com/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com/](https://my.dxc.com/)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
* URL: [https://my.dxc.com/robots.txt](https://my.dxc.com/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com](https://my.dxc.com)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com](https://my.dxc.com)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
* URL: [https://my.dxc.com/](https://my.dxc.com/)
  
  
  * Method: `GET`
  
  
  * Parameter: `AWSELB`
  
  
  * Evidence: `Set-Cookie: AWSELB`
  
  
  
  
* URL: [https://my.dxc.com/robots.txt](https://my.dxc.com/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
* URL: [https://my.dxc.com/sitemap.xml](https://my.dxc.com/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `saml_request_path`
  
  
  * Evidence: `Set-Cookie: saml_request_path`
  
  
  
  
Instances: 8
  
### Solution
<p>Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Ensure that the secure flag is set for cookies containing such sensitive information.</p>
  
### Reference
* http://www.owasp.org/index.php/Testing_for_cookies_attributes_(OWASP-SM-002)

  
#### CWE Id : 614
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
### Loosely Scoped Cookie
##### Informational (Low)
  
  
  
  
#### Description
<p>Cookies can be scoped by domain or path. This check is only concerned with domain scope.The domain scope applied to a cookie determines which domains can access it. For example, a cookie can be scoped strictly to a subdomain e.g. www.nottrusted.com, or loosely scoped to a parent domain e.g. nottrusted.com. In the latter case, any subdomain of nottrusted.com can access the cookie. Loosely scoped cookies are common in mega-applications like google.com and live.com. Cookies set from a subdomain like app.foo.bar are transmitted only to that domain by the browser. However, cookies scoped to a parent-level domain may be transmitted to the parent, or any subdomain of the parent.</p>
  
  
  
* URL: [https://my.dxc.com/sitemap.xml](https://my.dxc.com/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://my.dxc.com/robots.txt](https://my.dxc.com/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://my.dxc.com](https://my.dxc.com)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://my.dxc.com/](https://my.dxc.com/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://my.dxc.com/](https://my.dxc.com/)
  
  
  * Method: `GET`
  
  
  
  
Instances: 5
  
### Solution
<p>Always scope cookies to a FQDN (Fully Qualified Domain Name).</p>
  
### Other information
<p>The origin domain used for comparison was: </p><p>my.dxc.com</p><p>saml_request_path=/content/intranet/sitemap.xml</p><p>AWSELB="DF532BDD0CEC08C4DE4D1D1D93A98E75422B2F3DB69B94DC28BAD7F7B316A22388FF3AB15B93193749D8BFEE64D00484029E5F4772941DA642E79AAA40F08C0461C80F6615";$Path="/";$Domain="my.dxc.com"</p><p></p>
  
### Reference
* https://tools.ietf.org/html/rfc6265#section-4.1
* https://www.owasp.org/index.php/Testing_for_cookies_attributes_(OTG-SESS-002)
* http://code.google.com/p/browsersec/wiki/Part2#Same-origin_policy_for_cookies

  
#### CWE Id : 565
  
#### WASC Id : 15
  
#### Source ID : 3
