# guide-web-content-discovery-manualy

## Robots.txt

The robots.txt file is a document that tells search engines which pages they are and aren't allowed to show on their search engine results or ban specific search engines from crawling the website altogether. It can be common practice to restrict certain website areas so they aren't displayed in search engine results. These pages may be areas such as administration portals or files meant for the website's customers.

> Try: http://url or ip/robots.txt

## Favicon

The robots.txt file is a document that tells search engines which pages they are and aren't allowed to show on their search engine results or ban specific search engines from crawling the website altogether. It can be common practice to restrict certain website areas so they aren't displayed in search engine results. These pages may be areas such as administration portals or files meant for the website's customers [Favicon_Database_OWASP](https://wiki.owasp.org/index.php/OWASP_favicon_database).
See path favicon and download favicon get its md5 hash value which you can then lookup on the [Favicon_Database_OWASP](https://wiki.owasp.org/index.php/OWASP_favicon_database).

> Try: curl https://[url or ip]/[url or path favicon.ico] | md5sum

## Sitemap.xml

Unlike the robots.txt file, which restricts what search engine crawlers can look at, the sitemap.xml file gives a list of every file the website owner wishes to be listed on a search engine. These can sometimes contain areas of the website that are a bit more difficult to navigate to or even list some old webpages that the current site no longer uses but are still working behind the scenes.

> Try: http://[ip or url]/sitemap.xml

## HTTP Headers

When we make requests to the web server, the server returns various HTTP headers. These headers can sometimes contain useful information such as the webserver software and possibly the programming/scripting language in use.

> Try: curl http://[ip or url] -v

## OSINT - Google Hacking / Dorking

More info: https://wiki.elhacker.net/bugs-y-exploits/nivel-web/google-dorking

_Filter:_ site  
_Example:_ site:tryhackme.com  
_Description:_ returns results only from the specified website address  
_Filter:_ inurl  
_Example:_ inurl:admin
_Description:_ returns results that have the specified word in the URL  
_Filter:_ filetype  
_Example:_ filetype:pdf  
_Description:_ returns results which are a particular file extension  
_Filter:_ intitle  
_Example:_ intitle:admin  
_Description:_ returns results that contain the specified word in the title

## OSINT - Wayback Machine

The Wayback Machine (https://archive.org/web/) is a historical archive of websites that dates back to the late 90s. You can search a domain name, and it will show you all the times the service scraped the web page and saved the contents. This service can help uncover old pages that may still be active on the current website.

## OSINT - Wappalyzer

is an online tool and browser extension that helps identify what technologies a website uses, such as frameworks, Content Management Systems (CMS), payment processors and much more, and it can even find version numbers as well.
https://www.wappalyzer.com/

## Whatweb

[Documentation](https://www.kali.org/tools/whatweb/)

> Try: whatweb -v -a 3 [ip or url]

## OSINT - Github

Search on Github

## OSINT - S3 Buckets

S3 Buckets are a storage service provided by Amazon AWS, allowing people to save files and even static website content in the cloud accessible over HTTP and HTTPS. The owner of the files can set access permissions to either make files public, private and even writable. Sometimes these access permissions are incorrectly set and inadvertently allow access to files that shouldn't be available to the public. The format of the S3 buckets is http(s)://**{name}.s3.amazonaws.com** where {name} is decided by the owner, such as tryhackme-assets.s3.amazonaws.com. S3 buckets can be discovered in many ways, such as finding the URLs in the website's page source, GitHub repositories, or even automating the process. One common automation method is by using the company name followed by common terms such as **{name}**-assets, **{name}**-www, **{name}**-public, **{name}**-private, etc.

## Option Automated

> gobuster dir --url http://[ip or url]/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
