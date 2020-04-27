# nock-puppeteer
Mock http requests with Nock.js in puppeteer

## Motivation
Integration/E2E tests and scrapers need to mock puppeteer's browser http requests - why not to have the abilities of Nock.js?
"Nock works by overriding Node's http.request function" and when you run tests/scrapers with puppeteer the *browser* make the http requests 

## How does it work?
nock-puppeteer simply execute the requests instead of the browser with the help of puppeteer setRequestInterceptor hook.


## Basic Usage
const puppeteer = require('puppeteer');
 
(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.screenshot({path: 'example.png'});
 
  await browser.close();
})();


## Basic Usage