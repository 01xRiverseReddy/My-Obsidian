### Intro 

Web crawlers are primarily used to scout across the internet and pick up selective information . Their primary use cases are search engine indexing , malware detection etc . 

![[Pasted image 20250527203538.png]]
### Seed URLs
Seed URLs are the starting point of web crawler and decides the efficiency of the search engine/crawler . Seed URLs are sometimes manually decided for example if you are counting through book you might choose piratebase as a seed url or sometimes based on domains and the most popular websites etc . 

### URL Frontier 
This is the heart of the web crawler and decides factors such as politeness and freshness . Politeness is the rate at which the crawler makes requests to the request to the website Website and this is important because website might list you as DDOS attacker if you are request come in more frequently . Freshness s the factor that decides how frequently to revisit URL URL because some of the some of the sites are frequently such as new pages or blog post .

![[Pasted image 20250527204820.png]]


Front Q are what decide the freshness of the URLs and Bacque are the ones that decide the politeness front Queues Have F number of Q each Q representing its on rating rating of priority . Baccus represent the politeness and and the number of backs are equal directly to the number of threats that are running on fetch and renderer, so that no amount of computation is left, wasted and the web crawler improves its efficiency . One main reason why we are Not having the same number of front Q and back Q is because the number of threats running on fender could be different from rating of priority. We would want to the queue set.


### HTML Downloader/Renderer 

HTML downloader is connected directly to the DNS resolver so that the plane URL can be converted to IP addresses and the HTML pages can be downloaded after the HTML pages are downloaded. It is necessary to render the pages because some of the pages may be malformed/error and some of the pages might be malicious. 

### Content Parser 

Content parcel reads through the HTL that has been downloaded and store it in the storage. If the content is fresh, the way decides if a content is fresh or not is through a high signature. Google uses harsh functions like Simmi Hash to determine if a page has been already visited. 

### URL Extractor and filter 

From the downloaded HTML pages, the URL extractor extracts all the URL that have been found on the page and then it passes it to the URL filter. And the reason it touch this is because some of the URL might have images some of the URL might have links to content delivery networks or videos which are often not required by the Web crawler, and if the URL has been already been visited, the URL is excluded and if the URL is fresh, it is that it is then passed back onto the URL frontier. The already visited URL are stored on this special data structure called URL storage, not not much familiar about regarding that, but might look into it. 

Literature 
[[System Design Web Crawler]]
[[How are seed URLs decided]]