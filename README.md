# Advanced Google Analytics (2017)

Notes on the Advanced Google Analytics course on lynda.com

Warning: Content of this course is outdated. Google Search Console has been updated since this course was published.

## Prerequisites

- Google Webmaster Tools (Search Console)

## Things to do

- Set up Search Console
- Create segments

## SEO performance measurement

- Search Console
  - link to find market share of organic search
  - IDEA: see high bounce rate on landing pages
  - page load speed
  - EXAMPLE:
    - Segment: mobile and tablet traffic (vs all)
    - Landing pages and avg session duration
  - indexing and crawl statistics
    - Search Console > Crawl errors
      - to find technical issues on site
- IDEA: Use search engine traffic as segment
  - to compare performance of different search engines

## Advanced setup

- TODO: Use views for subdomains
- advanced filters and views
  - Admin > View > Filter > custom filter
  - IDEA: Create filter for a specific location (e.g. Mountain View, USA)
  - Can use advanced filters with wildcards definitions and regex
  - Can combine two advanced filters and custom filters
    - e.g. filter out users referred from LinkedIn AND PayPal
- custom dimensions and metrics
  - Admin > Property > Custom definitions > Custom dimensions/metrics
    - requires implementation in code, automatically generates code snippet
      - must follow google developers guide
    - will then be available in reports

## Doing more with analytics

- Weighted sort
  - to filter out statistically insignificant results
  - not available for all metrics
  - TIP: set row number to maximum, export to excel, then use excel filter to apply weights (e.g, greater than 100)
- User intent
  - Q: what keywords, search terms are being used?
  - Q: Are there any search patterns? 
  - Q: Top internal searches?
  - Q: What page did users search on? What page path?
  - Q: Which site is the referrer?
  - Q: Did search improve goal conversion?
    - users who search vs users who don't search
  - Q: can we run an experiment to steer users?
  - Q: What is the page depth? What did users go to after a search?
  - Q: What is the bounce rate on search pages?
- IDEA: Set up site search
  - site search is set up for each view
  - Admin > View > View Settings > Site search Tracking > ON 
  - enter query parameter
  - report shows up in Behavior > Site search > Search terms/pages
  - IDEA: Site Content > All pages > Secondary dimension: Previous page path > search bar: query parameter (e.g. s=)
    - this lets you see search terms
- [Page Analytics](https://chrome.google.com/webstore/detail/page-analytics-by-google/fnbdnhhicmebfgdgglcdacdapkcihcoh?hl=en) tool - Chrome extension
  - for in-page analytics
  - can view metrics for different parts of page for actual page being viewed
  - beware of differences based on when parts of page are updated
  - set date range to avoid issues
- TODO: Using content grouping
  - use to group content
  - Admin > View > Content grouping
  - NOTE: not retroactive. So create early
  - Once set up, groupings will show up in reports as a primary dimension
  - 3 ways
    - modify tracking code on pages
    - extract content based on URL
    - rule definitions
- Using regex
  - e.g. to exclude all IP addresses for all employees
  - metacharacters ([link to video](https://www.lynda.com/Google-Analytics-tutorials/How-use-regex-Metacharacters/653250/676722-4.html?srchtrk=index%3a2%0alinktypeid%3a2%0aq%3agoogle+analytics%0apage%3a1%0as%3arelevance%0asa%3atrue%0aproducttypeid%3a2))
    - \, |, ?, 
  - TODO: Learn how to use regex
