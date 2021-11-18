# Actor - Traffic Generator

## Traffic Generator

This actor helps you to generate traffic into your website. If you want some pageviews or test your website with how much load it'll going to process, you are on the good spot.

The Traffic Generator supports the following features:

-   Generate Pageviews - The actor can generate pageview for Google on any of the target websites.

-   Generate Stress and Load - The actor can generate stress on the target websites. It is good for testing purposes.

-   Enable Crawling - The actor can be able to crawl the website to generate the traffic or stress over multiple pages.

-   Kill Switch - The actor can kill itself and duplications after a certain time.

-   Duplicate the current run - The actor can duplicate itself to run on multiple instances. Basically it will parallelize the work and multiply the power of it.


## Bugs, fixes, updates and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/tugkan/traffic-generator/issues).

## Setup & Usage

You can see how this actor works these videos:

### Using Search

[![Apify - XXXXX Scraper - Using Search](https://img.youtube.com/vi/7rpRBlIE--o/0.jpg)](https://www.youtube.com/watch?v=7rpRBlIE--o)

You can check the output of this example [here](https://api.apify.com/v2/datasets/AVTdGvcS2iOjDgAaV/items?clean=true&format=json).

### Using Start URLs

[![Apify - XXXXX Scraper - Using Start URLs](https://img.youtube.com/vi/ProePJ_1pwA/0.jpg)](https://www.youtube.com/watch?v=ProePJ_1pwA)

You can check the output of this example [here](https://api.apify.com/v2/datasets/yiZ9wm15WMTdmdH8L/items?clean=true&format=json).

## Input Parameters

The input of this scraper should be JSON containing the list of pages that should be visited. Required fields are:

| Field                | Type    | Description                                                                                                                                                                                                    |
| -------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| mode               | String  | (required) Mode of the actor. It can be PAGEVIEW or STRESS_TEST.                                                                                                                                                       |
| enableCrawling       | Boolean | (optional) This option will enable the crawling capabilities of the actor. If you enable this option the actor will scrape all the links that if finds on the website. |
| startUrls            | Array   | (required) List of URLs that you want to create requests on.                                                                                                                 |
| endPage              | Integer | (optional) Final number of page that you want to scrape. Default is `Infinite`. This is applies to all `search` request and `startUrls` individually.                                                          |
| endAfterSeconds             | Integer | (optional) You can limit the time on the actor. Basically if you want to kill the actor after a certain number of seconds, you should enable and fill this field.                                                                                                |
| duplicateActor             | Integer | (optional) This option will duplicate the current run with this number. Please keep in mind that the load on the website will be multiplied by this number.                                                                                                |
| proxy                | Object  | Proxy configuration                                                                                                                                                                                            |


This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

##### Tip

`PAGEVIEW` mode triggers Puppeteer instance and waits for Pageview responses. If you want to generate traffic on the target, that option should be selected.

If you want to generate traffic (or stress) on the website in general - not a single URL - then you should enable this option. This option will scrape all the links it encounters and adds them into the queue.

Please keep in mind that actor duplication is a very strong option to generate traffic into the website. Ex: If you fill this field by 3, then the actor will clone itself and run by 4 runs in total. However you should always keep in mind that there is a limitation that you have on Apify (memory or CUs) which you can find on your dashboard.

The actor runs forever unless you abort it. Thats why you should always set the option of `endAfterSeconds`. If you want to generate a traffic constantly then keep this option as empty.


### Compute Unit Consumption

The actor optimized to run blazing fast and scrape many as listings as possible. Therefore, it forefronts all requests. If actor doesn't block very often it'll scrape 100 pages in 2 minutes with ~0.03-0.05 compute units.

### Traffic Generator Input example

```json
{
  "mode":"PAGEVIEW",
  "startUrls":[
    "https://apify.com/"
  ],
  "enableCrawling":true,
  "duplicateActor": 2,
  "waitForPageview":true
}

```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.

If you provide incorrect input to the actor, it will immediately stop with failure state and output an explanation of what is wrong.
