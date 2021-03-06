# Web Scraping 

## Web Scrape with Python in 4 minutes 

***Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.***

### Important notes about web scraping: 

1. Read through the website’s Terms and Conditions to understand how you can legally use the data.
2. Make sure you are not downloading data at too rapid a rate because this may break the website.

### Python Code 

            # Import libraries
            import requests
            import urllib.request
            import time
            from bs4 import BeautifulSoup

            # Set the URL you want to webscrape from
            url = 'http://web.mta.info/developers/turnstile.html'

            # Connect to the URL
            response = requests.get(url)

            # Parse HTML and save to BeautifulSoup object¶
            soup = BeautifulSoup(response.text, "html.parser")

            # To download the whole data set, let's do a for loop through all a tags
            line_count = 1 #variable to track what line you are on
            for one_a_tag in soup.findAll('a'):  #'a' tags are for links
                if line_count >= 36: #code for text files starts at line 36
                    link = one_a_tag['href']
                    download_url = 'http://web.mta.info/developers/'+ link
                    urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:]) 
                    time.sleep(1) #pause the code for a sec
                #add 1 for next line
                line_count +=1 

## What is Web Scraping ?

***Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet.***

***Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page). Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet or loaded into a database. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else. An example would be to find and copy names and telephone numbers, or companies and their URLs, or e-mail addresses to a list.***

***Web scraping is used for contact scraping, and as a component of applications used for web indexing, web mining and data mining, online price change monitoring and price comparison, product review scraping (to watch the competition), gathering real estate listings, weather data monitoring, website change detection, research, tracking online presence and reputation, web mashup and, web data integration.***

***Web pages are built using text-based mark-up languages (HTML and XHTML), and frequently contain a wealth of useful data in text form.***

## How to scrape websites without getting blocked 

***Web scraping is a task that has to be performed responsibly so that it does not have a detrimental effect on the sites being scraped.***

### Web Scraping best practices to follow to scrape without getting blocked 

* Respect Robots.txt : 

*Web spiders should ideally follow the robot.txt file for a website while scraping. It has specific rules for good behavior such as how frequently you can scrape, which pages allow scraping, and which ones you can’t. Some websites allow Google to scrape their websites, by not allowing any other websites to scrape. This goes against the open nature of the Internet and may not seem fair but the owners of the website are within their rights to resort to such behavior.*

* Make the crawling slower, do not slam the server, treat websites nicely

*Web scraping bots fetch data very fast, but it is easy for a site to detect your scraper as humans cannot browse that fast. The faster you crawl, the worse it is for everyone. If a website gets too many requests than it can handle it might become unresponsive.* 

*Use auto throttling mechanisms which will automatically throttle the crawling speed based on the load on both the spider and the website that you are crawling. Adjust the spider to an optimum crawling speed after a few trials runs. Do this periodically because the environment does change over time.* 

* Do not follow the same crawling pattern 

*Web scraping bots tend to have the same crawling pattern because they are programmed that way unless specified. Sites that have intelligent anti-crawling mechanisms can easily detect spiders by finding patterns in their actions and can lead to web scraping getting blocked.*

*Incorporate some random clicks on the page, mouse movements and random actions that will make a spider look like a human.*

* Make requests through Proxies and rotate them as needed 

*When scraping, your IP address can be seen. A site will know what you are doing and if you are collecting data. They could take data such as – user patterns or experience if they are first time users.*

*Multiple requests coming from the same IP will lead you to get blocked, which is why we need to use multiple addresses. When we send requests from a proxy machine, the target website will not know where the original IP is from, making the detection harder.* 

*There are several methods can be used to change your outgoing IP.*

1. TOR
2. VPNs
3. Free Proxies 

* Rotate User Agents and corresponding HTTP Request Headers between requests 

*A user agent is a tool that tells the server which web browser is being used. If the user agent is not set, websites won’t let you view content. Every request made from a web browser contains a user-agent header and using the same user-agent consistently leads to the detection of a bot. You can get your User-Agent by typing ‘what is my user agent’ in Google’s search bar. The only way to make your User-Agent appear more real and bypass detection is to fake the user agent. Most web scrapers do not have a User Agent by default, and you need to add that yourself.* 

*The most basic ones are:*

1. User-Agent
2. Accept
3. Accept-Language
4. Referer
5. DNT
6. Updgrade-Insecure-Requests
7. Cache-Control 

* Use a headless browser like Puppeteer, Selenium or Playwright 

*The simplest check is if the client (web browser) can render a block of JavaScript. If it doesn’t, then it pretty much flags the visitor to be a bot. While it is possible to block running JavaScript in the browser, most of the Internet sites will be unusable in such a scenario and as a result, most browsers will have JavaScript enabled.* 

*Once this happens, a real browser is necessary in most cases to scrape the data. There are libraries to automatically control browser such as*

1. Selenium
2. Puppeteer and Pyppeteer
3. Playwright

* Beware of Honey Pot Traps 

*Honeypots are systems set up to lure hackers and detect any hacking attempts that try to gain information. It is usually an application that imitates the behavior of a real system. Some websites install honeypots, which are links invisible to normal users but can be seen by web scrapers.* 

* Avoid scraping data behind a login 

*Login is basically permission to get access to web pages. Some websites like Indeed and Facebook do not allow permission.* 

*Its generally preferred to avoid scraping websites that have a login as you will get blocked easily, but one thing you can do is imitate human browsers whenever authentication is required you get the target data you need.* 

* Use Captcha Solving Services 

*Many websites use anti web scraping measures. If you are scraping a website on a large scale, the website will eventually block you. You will start seeing captcha pages instead of web pages. There are services to get past these restrictions such as 2Captcha or Anticaptcha.*

*If you need to scrape websites that use Captcha, it is better to resort to captcha services. Captcha services are relatively cheap, which is useful when performing large scale scrapes.*

* How can websites detect and block web scraping ?

*Websites can use different mechanisms to detect a scraper/spider from a normal user. Some of these methods are enumerated below:*

1. Unusual traffic/high download rate 
2. Repetitive tasks performed on the website in the same browsing pattern 
3. Checking if you are real browser 
4. Detection through honeypots  

* How do you find out if a website has blocked or banned you ?

*If any of the following signs appear on the site that you are crawling, it is usually a sign of being blocked or banned.*

1. CAPTCHA pages
2. Unusual content delivery delays
3. Frequent response with HTTP 404, 301 or 50x errors

*Frequent appearance of these HTTP status codes is also indication of blocking*

1. 301 Moved Temporarily
2. 401 Unauthorized
3. 403 Forbidden
4. 404 Not Found
5. 408 Request Timeout
6. 429 Too Many Requests
7. 503 Service Unavailable


