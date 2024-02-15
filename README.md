# Traffic Generator Actor

## What is Traffic Generator actor?
The Traffic Generator Actor is an advanced, automated tool on Apify that simulates user traffic to your digital platforms on any web page, YouTube video, Etsy shop, Behance profile, and more. Whether you’re aiming to boost your SEO rankings or put your site’s durability to the test, this actor is your digital key.


### Key features
- 📈 Generate Page Views: Creates unique visits to elevate your site's SEO and visibility on platforms like Google, Etsy, and Behance.
- 🎥 Generate YouTube View Counts: Instantly boosts view counts for YouTube videos, enhancing their popularity.
- 💪 Generate Stress and Load: Puts your site through rigorous testing to ensure stability during high traffic peaks.
- 🕷️ Enable Crawling: Mimics user behavior across multiple pages, if you have multiple links on the webpage you want to generate traffic, the actor will handle them too.
- ⏱️ Kill Switch: Automatically stops and replicates the process after a set time so that you will be in control.
- 🧑‍🤝‍🧑 Duplicate Current Run: Scales up the operation by running multiple actors simultaneously.


## Use Cases | Who Can Use Traffic Generator
- SEO experts looking to **increase organic traffic on any targeted web page** such as blog sites.
- Webmasters **preparing for high-traffic events or campaigns**.
- Developers need to **test website limits** via stress tests.
- Digital marketers aiming to **enhance web analytics data**.
- **Etsy shop owners** who want to increase visits to their shops.
- Designers looking to enhance their **Behance profile views**.
- Youtubers wishing to **increase YouTube video views**.


## Input
Add any website, profile, or video URL that you want to create traffic to the input area.
![](https://cdn.epctex.com/actors/traffic-generator/1.png)

Choose whether you want to generate pageviews or make a stress test.
![](https://cdn.epctex.com/actors/traffic-generator/2.png)

Example JSON:
```json
{
    "mode": "PAGEVIEW",
    "startUrls": ["https://apify.com/"],
    "enableCrawling": true,
    "enableYoutube": false,
    "duplicateActor": 2,
    "waitForPageview": true
}
```


### Input Parameters Explained
- `enableCrawling`: (Optional)

	If the webpage you want to increase traffic to, has multiple links and subpages, the actor will also work and increase traffic to these pages.
- `enableYoutube`: (Optional) (Experimental Feature)

    This feature is for YouTube videos. For more information, check “Example Input Scenario” after this section. 👇
- `waitOnPage`: (Optional) (Only on Pageview Mode)

	How much time that the actor stay on each of the pages. If you want to specify the number of seconds that the actor will spend on every page, you should enable and fill this field.
- `endAfterSeconds`: (Optional)

    You can limit the time of working of the actor. Basically, if you want to kill the actor after a certain number of seconds, you should enable and fill this field.

    The actor runs forever unless you abort it. That's why you should always set the option of endAfterSeconds. If you want to generate traffic constantly then keep this option as empty.
- `duplicateActor`: (Optional)

	This option will duplicate the current run with this number. Please keep in mind that the load on the website will be multiplied by this number.

    Remember great power comes with great responsibility. If you want to double the actor number, make sure to do it under control. If you fill this field by 3, then the actor will clone itself and run by 4 runs in total. However, you should always keep in mind that there is a limitation that you have on Apify (memory or CUs) which you can find on your dashboard.

    This option is created for stress-load tests.
- `proxy`: (Required) (Proxy Object)
    Proxy configuration.

This solution requires the use of Proxy servers, either your proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).


### Example Input Scenario 1: How to Generate YouTube Video View?
For instance, if you want the actor to stay for 2 minutes in your Youtube video; set the “wait on page” value to 120 seconds, and set the “end after” value as 1200 seconds to produce 10 views. After 1200 seconds, the actor will stop working.

(Don’t forget to switch to Youtube Pageview test on)
![](https://cdn.epctex.com/actors/traffic-generator/3.png)

It is recommended to keep advanced options and run options as default.
![](https://cdn.epctex.com/actors/traffic-generator/4.png)

Here's its equivalent in JSON:
![](https://cdn.epctex.com/actors/traffic-generator/5.png)


### Example Input Scenario 2: How to Generate Webpage Traffic?
If you want to create web traffic, after entering the URL of the page, just run the actor.

Note that if the website has subpages, and you wish to increase their traffic too, switch on the “enable crawling”.
![](https://cdn.epctex.com/actors/traffic-generator/6.png)

It is recommended to keep advanced options and run options as default.
![](https://cdn.epctex.com/actors/traffic-generator/7.png)


## Output
Check the analytics of your website while the actor runs, you will see the results in minutes!


### Important Note
The Traffic Generator Actor is a powerful tool designed to significantly elevate traffic across various platforms, **but please note it doesn’t store its operational data in a dataset. Monitor the Traffic Generator's effectiveness directly through your analytics dashboard.**

Please keep in mind that actor duplication is a very strong option to generate traffic to the website. Ex: If you fill this field by 3, then the actor will clone itself and run by 4 runs in total. However, you should always keep in mind that there is a limitation that you have on Apify (memory or CUs) which you can find on your dashboard.

The actor runs forever unless you abort it. That's why you should always set the option of `endAfterSeconds`. If you want to generate traffic constantly then keep this option as empty.


## During the Run
During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.


### Compute Unit Consumption
The actor is optimized to run blazing fast and scrape as many listings as possible. Therefore, it forefronts all requests. If the actor doesn't block very often it'll scrape 100 pages in 2 minutes with ~0.03-0.05 compute units.


## Bugs, fixes, updates, and changelog
This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/traffic-generator/issues).

## How to use Traffic Generator
https://www.youtube.com/watch?v=5tXygwPJmJ8&ab_channel=epctex

## FAQ
**Can the Traffic Generator Actor improve my website's SEO?**<br/>
Yes! By increasing pageviews, it can help boost your site's ranking on search engines. 🚀

**Is it safe to use for my website?**<br/>
Absolutely. The kill switch feature ensures it stops before causing any issues. 🛡️

**How can I track the traffic generated?**<br/>
Keep an eye on your site's analytics dashboard to see the real-time impact. 📊

**Will this work for video platforms like YouTube?**<br/>
Yes, it has a feature to increase YouTube view counts. 🎥

**Can I control how long the actor runs?**<br/>
Yes, you can set a specific duration with the endAfterSeconds parameter. ⏳

**What if I have a large website and want to generate comprehensive traffic?**<br/>
Enable the duplicateActor option to scale up the traffic generation across your site. 🌐


## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
