### Introduction
PwnRedirect, a simple python script that probes for Open Redirection vulnerability in a website. It does that by fuzzing the URL that is provided in the input. PwnRedirect is a powerful tool designed to detect open redirect vulnerabilities on websites. These vulnerabilities are often serious security holes, allowing attackers to take advantage of redirect functionality on websites to redirect legitimate users to malicious domains. This tool is particularly useful for security researchers, bug bounty hunters and penetration testing teams in identifying and reporting open redirect vulnerabilities quickly and effectively.

PwnRedirect works by sending a number of specialized payloads to URL parameters that are vulnerable to redirection, such as `?redirect=`, `?next=`, or `?url=`. This payload is usually a URL that will test whether the web application is redirecting insecurely. If the website responds with a redirect to an unwanted location (such as the malicious site specified by the payload), then the tool will identify it as an open redirect vulnerability.

### Features
PwnRedirect can identify following types of Open Redirect Vulnerabilities:
 - **Payload-Based Scanning:** The tool supports a variety of common redirection payloads that can be changed or added by users to customize security testing to their specific needs.
 - **Automated Testing:** The tool sends automated HTTP requests for each URL and payload combination, enabling bulk testing of various website endpoints.
 - **Easy-to-read Result Logging:** If an open redirect vulnerability is found, the tool will clearly display the result in the terminal, making it easy to identify the problematic endpoint.


Also, Oralyzer has its own module to fetch URLs from web.archive.org, it then separates the URLs that have specific parameters in them, parameters that are more likely to be vulnerable.

### Installation
1. Instalasi Pwnredirect Dependencies
```
$ git clone lamcodeofpwnosec/pwnredirect.git
$ pip3 install -r requirements.txt
```
2. Setting Up Payloads
By default, the tool comes with a payloads.txt file, which contains a number of payloads that can be used to test the website. If you want to add custom payloads, you can edit the payloads.txt file or create a new payload file.
Example of the contents of payloads.txt:
```sh
/?url=http://evil.com
/?next=http://evil.com
/?redirect=http://evil.com
/?redir=http://evil.com
/?target=http://evil.com
/?out=http://evil.com
```
Once all the settings are complete, you can run the tool with the following command:
```
python3 pwnredirect.py <URL> -p <payload file>
```
### Features

- [x] Improved DOM XSS detection mechanism
- [x] Test multiple parameters in one run
- [x] CRLF Injection Detection

### Contribution

You can contribute to this project in following ways:

- Create pull requests
- Report bugs
- Hit me up on <a href='http://instagram.com/lamcodeofpwnosec'>Instagram</a> with a new idea/feature
