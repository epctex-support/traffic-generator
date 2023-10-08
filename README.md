# Actor - Traffic Generator

## Traffic Generator

This actor helps you to generate traffic to your website. If you want some pageviews or test your website with how much load it'll going to process, you are in a good spot.

The Traffic Generator supports the following features:

-   Generate Pageviews - The actor can generate pageviews for Google on any of the target websites.

-   Generate Youtube View Counts - Generate view counts immediately on Youtube!

-   Generate Stress and Load - The actor can generate stress on the target websites. It is good for testing purposes.

-   Enable Crawling - The actor can be able to crawl the website to generate traffic or stress over multiple pages.

-   Kill Switch - The actor can kill itself and duplicates after a certain time.

-   Duplicate the current run - The actor can duplicate itself to run on multiple instances. It will parallelize the work and multiply the power of it.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/traffic-generator/issues).

## Input Parameters

The input of this scraper should be JSON containing the list of pages that should be visited. Possible fields are:

- `startUrls`: (Required) (Array) List of URLs that you want to create requests on.

- `mode`: (Required) (String) Mode of the actor. It can be PAGEVIEW or STRESS_TEST.

- `enableYoutube`: (Optional) (Boolean) Let the actor play the Youtube videos. The mode has to be `PAGEVIEW`. Please set `waitOnPage` attribute for the best experience.

- `waitOnPage`: (Optional) (Number) (Only on Pageview Mode) How much time that the actor will stay on each of the pages. If you want to specify the number of seconds that the actor will spend on every page, you should enable and fill this field.

- `endAfterSeconds`: (Optional) (Number) You can limit the time on the actor. Basically, if you want to kill the actor after a certain number of seconds, you should enable and fill this field.

- `duplicateActor`: (Required) (Number) This option will duplicate the current run with this number. Please keep in mind that the load on the website will be multiplied by this number.

- `enableCrawling`: (Optional) (Boolean) This option will enable the crawling capabilities of the actor. If you enable this option the actor will scrape all the links that if finds on the website.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

This solution requires the use of **Proxy servers**, either your proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

`PAGEVIEW` mode triggers the Puppeteer instance and waits for Pageview responses. If you want to generate traffic on the target, that option should be selected.

If you want to generate traffic (or stress) on the website in general - not a single URL - then you should enable this option. This option will scrape all the links it encounters and adds them to the queue.

Please keep in mind that actor duplication is a very strong option to generate traffic to the website. Ex: If you fill this field by 3, then the actor will clone itself and run by 4 runs in total. However, you should always keep in mind that there is a limitation that you have on Apify (memory or CUs) which you can find on your dashboard.

The actor runs forever unless you abort it. That's why you should always set the option of `endAfterSeconds`. If you want to generate traffic constantly then keep this option as empty.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape many listings as possible. Therefore, it forefronts all requests. If the actor doesn't block very often it'll scrape 100 pages in 2 minutes with ~0.03-0.05 compute units.

### Traffic Generator Input example

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

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
