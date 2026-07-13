# Enabling HTTPS with Let's Encrypt & Certbot  

The process is explained well on Lab Activity 3a1  

Here are some additional reflection questions:  

## Refelction Questions  

* Why is HTTPS important for modern web applications?

HTTPS stands for Hypertext Transfer Protocol Secure. It is very critical for three reasons. Firstly, It scrambles the dat travelling between a user's browser and the web server. This prevents attackers from eavesdropping on sensitive information like passwords, credit card numbers or personal messages. Secondly, It proves to the user that they are communicating with the legitimate server they intended to reach, preventing the man-in-the-middle attacks where a hacker intercepts and impersonate the site. Lastly, it ensures that the data being transfered cannot be modified or corrupted in transit without being detected. The search engines heavily penalize non-HTTPS sites, and modern browsers actively flag them with prminent 'Not Secure' warnings.  

  
* What entity issued your site's TLS certificate?

  The Issuer is Let's Encrypt. It is a free, automated, and open certificate authority run by the non-profit Internet Security Research Group.

  <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/23fc3329-1fc1-4c61-aa06-fcac9c6fd644" />

  
  
* How long is your certificate valid for, and how can it be renewed?

  Let's Encrypt certificates are valid for exactly 90 days from the date of issue. They are designed to be renewed automatically. This is usually handled by the certbot software running a background task (via a cron job or ysytemd timer) that checks for expiring certificates and sutomatically renew them. Of course Manually renew it by running the command 'sudo certbot renew' is totally possible.

  
* What happens if a certificate expires and is not renewed?

  When a certificates expires, the trust chain is broken. Modern browsers will immediately block users from accessing the site, displaying a massive, intimidating warning page (often reading "Your connection is not private" or ERR_CERT_DATE_INVALID). Users have to manually click through advanced settings to bypass the warning, which severely damage the site's credibility and drives traffic away.
  
* Why does Let's Encrypt require port 80 or 443 to be open for verification?

  Let's Encrypt issues certificates for free, but it must mathematically verify that you actually own the server and domain you are claiming. It does this using the ACME protocol. When the user request a certificate, Let's Encrypt gives a unique digital token. Let's Encrypt's external servers then attempt to access that token by making a standard web request to the server's IP address. Web traffic uses port 80 (HTTP) or port 443 (HTTPS). If the firewall blocks these ports, Let's Encrypt cannot reach the token, the domain validation fails, and the certificate is denied.
  
