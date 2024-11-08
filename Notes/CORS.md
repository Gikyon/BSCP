# CORS (Cross Origin Resource Sharing)
  This is a policy where a server (domain) allows other trusted domains to access objects (resources) from their server. 
  Typically these attacks are used to exfiltrate datas. Now, How do we detect and exploit these vulnerabilities? Well I will try my best to explain it.

  [What is a domain?](https://github.com/Gikyon/BSCP/edit/main/Notes/CORS.ml#what-is-a-domain)\
  [Tell-Tell Sign]()\
  [Exploitation]()\
  [Bypassing Security Measure]()\
  [Methodology]()
  
## What is a domain?
  I am sure you are familiar with the term domain. However, for the new people that's reading I would like to explain it briefly. 
  In this context, the domain that I am referring to is the URL that you use to access a website. Let's take a look at an URL and break it down:
  
http://sub.dom.com 
  
  sub: subdomain\
  dom: domain\
  com: top level domain\
  In a nutshell I like to think of it like a physical address, top level domain as your country, domain as your block, and subdomain is different houses that you own.
  now that you already recoganize what domains can look like. Let's see how we can tell if it is vulnerable to CORS attack.

## Tell-Tell Sign
  We can detect if a server employs this policy by looking at the response header. 
  There is a header specifically for CORS that is `Access-Control-Allow-Credentials: True`, True means the policy is present. 
  But, for us to know **what** domain it trust is by enumurating it. 
  Sending a request with the `Origin: https://domain.com` header can be one way to see if it trust it.
  If you sent a request with the origin header that the website trust it will return both `Access-Control-Allow-Credentials: True` and `Access-Control-Allow-Origin: https://your-domain.com` header.
  Otherwise, if it is not in the white list and CORS is present it will only response with the `Access-Control-Allow-Credentials: True` header.


  
