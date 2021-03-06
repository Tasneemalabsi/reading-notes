# Web Scraping

*Web scraping is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser.*

- Newer forms of web scraping involve monitoring data feeds from web servers. For example, JSON is commonly used as a transport storage mechanism between the client and the web server.

- There are methods that some websites use to prevent web scraping, such as detecting and disallowing bots from crawling (viewing) their pages. 

- There are web scraping systems that rely on using techniques in DOM parsing, computer vision and natural language processing to simulate human browsing to enable gathering web page content for offline parsing.

## Techniques

### Human copy-and-paste

The simplest form of web scraping is manually copying and pasting data from a web page into a text file or spreadsheet.

### Text pattern matching

A simple yet powerful approach to extract information from web pages can be based on the UNIX grep command or regular expression-matching facilities of programming languages (for instance Perl or Python).

### HTTP programming


Static and dynamic web pages can be retrieved by posting HTTP requests to the remote web server using socket programming.

### HTML parsing

Data of the same category are typically encoded into similar pages by a common script or template. In data mining, a program that detects such templates in a particular information source, extracts its content and translates it into a relational form, is called a wrapper.

### DOM parsing

By embedding a full-fledged web browser, such as the Internet Explorer or the Mozilla browser control, programs can retrieve the dynamic content generated by client-side scripts.

### Vertical aggregation

There are several companies that have developed vertical specific harvesting platforms. These platforms create and monitor a multitude of "bots" for specific verticals with no "man in the loop" (no direct human involvement), and no work related to a specific target site. 

### Semantic annotation recognizing
The pages being scraped may embrace metadata or semantic markups and annotations, which can be used to locate specific data snippets.

### Computer vision web-page analysis

There are efforts using machine learning and computer vision that attempt to identify and extract information from web pages by interpreting pages visually as a human being might.

## Methods to prevent web scraping

- Blocking an IP address either manually or based on criteria such as geolocation and DNSRBL. 
- Disabling any web service API that the website's system might expose.
- Bots sometimes declare who they are (using user agent strings) and can be blocked on that basis using robots.txt; 'googlebot' is an example. 
- Bots can be blocked by monitoring excess traffic
- Bots can sometimes be blocked with tools to verify that it is a real person accessing the site, like a CAPTCHA. 

## Web Scraping best practices to follow to scrape without getting blocked

1. Respect Robots.txt
2. Make the crawling slower, do not slam the server, treat websites nicely
3. Do not follow the same crawling pattern
4. Make requests through Proxies and rotate them as needed
5. Rotate User Agents and corresponding HTTP Request Headers between requests
6. Use a headless browser like Puppeteer, Selenium or Playwright
7. Beware of Honey Pot Traps
8. Check if Website is Changing Layouts
9. Avoid scraping data behind a login
10. Use Captcha Solving Services

### Respect Robots.txt

*Web spiders should ideally follow the robot.txt file for a website while scraping. It has specific rules for good behavior, such as how frequently you can scrape, which pages allow scraping, and which ones you can???t.*

If robot.txt contains lines like the ones shown below, it means the site doesn???t like and does not want to be scraped.

`User-agent: *`

`Disallow:/ `

**Here are a few easy giveaways that you are bot/scraper/crawler :**

- Scraping too fast and too many pages, faster than a human ever can
- Following the same pattern while crawling. 
- Too many requests from the same IP address in a very short time
- Not identifying as a popular browser. You can do this by specifying a ???User-Agent???.
- using a user agent string of a very old browser.

### Use a headless browser like Puppeteer, Selenium or Playwright

Anti Scraping tools are smart and are getting smarter daily, as bots feed a lot of data to their AIs to detect them. Most advanced Bot Mitigation Services use Browser Side Fingerprinting (Client Side Bot Detection)  by more advanced methods than just checking if you can execute Javascript.

*Bot detection tools look for any flags that can tell them that the browser is being controlled through an automation library.*

1. Presence of bot specific signatures
2. Support for nonstandard browser features
3. Presence of common automation tools such as Selenium, Puppeteer, Playwright, etc.
4. Human-generated events such as randomized Mouse Movement, Clicks, Scrolls, Tab Changes etc.

Workarounds or tools which could help your headless browser-based scrapers from getting banned:

1. Puppeteer Extra  ??? Puppeteer Stealth Plugin
2. Patching Selenium/ Phantom JS ??? Stack OverFlow Answer on Patching Selenium with Chrome Driver
3. Fingerprint Rotation ??? Microsoft Paper on Fingerprint Rotation.

### How do you find out if a website has blocked or banned you?

*Frequent appearance of these HTTP status codes is also indication of blocking*

- 301 Moved Temporarily
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 408 Request Timeout
- 429 Too Many Requests
- 503 Service Unavailable

## New York MTA Data

Turnstile data is compiled every week from May 2010 to present, so hundreds of .txt files exist on the site. Below is a snippet of what some of the data looks like

## Python Code


`import requests`

`import urllib.request`

`import time`

`from bs4 import BeautifulSoup`

`url = 'http://web.mta.info/developers/turnstile.html'`

`response = requests.get(url)`

`soup = BeautifulSoup(response.text, ???html.parser???)`

`soup.findAll('a')`

`one_a_tag = soup.findAll(???a???)[38]`

`link = one_a_tag[???href???]`

`download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])`

`time.sleep(1)`

