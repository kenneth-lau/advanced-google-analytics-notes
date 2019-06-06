# Advanced Google Analytics (2017)

Notes on the [Advanced Google Analytics](https://www.lynda.com/Google-Analytics-tutorials/Advanced-Google-Analytics/653250-2.html) course on lynda.com

Warning: Content of this course is outdated. Google Search Console has been updated since this course was published.

## Prerequisites

- Google Webmaster Tools (Search Console)

## Problem

- Google demo account doesn't allow creating new views

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

## Advanced reporting

- Custom team reports
  - can search shared custom reports in gallery
  - or create your own from precise metrics required
  - e.g. avg page load time (metrics group), device category (dimension)
  - can use multiple metrics groups
  - can select dimensions and order dimensions in dimensions drilldown
  - TODO: look at gallery of custom reports and customize for myself
- Build operational dashboards
  - Can select widgets and metrics for individual purpose
- C-level dashboards
  - broad level, global view
  - can get more specific as we go down
  - widget examples
    - total visits
    - avg visit duration
    - visit by device category (pie chart)
    - changes in bounce rate (%)
    - visits and avg vist duration by country
    - world map
    - list of top performing countries

## Cross-domain tracking and site linking

- View users movement between two sites (two domains) as a single session
- "Site linking"
  - if user goes to site A then goes to site B it will be counted as a single user and session
  - if you have multiple domains and various subdomains and want one integrated analytics report
  - if you have iframes on other sites - you can use site linking
- Setting up site linking (see developer guide)
  - requires JavaScript and HTML
  - need to modify tracking code
  - Step 1: primary domain - edit code
  - use auto link plugin
  - Step 2: secondary domain - also requires changes
  - Step 3: Create a copy of the reporting view by adding an advanced filter to the new view
  - Step 3 (option 2): Modify code in Tag Manager (not covered)
- Fault reporting with segmenting
  - to answer questions from management
  - create segments (e.g. bing and google search results)
  - then compare against previous period
  - then share report with management

## Conversion rate analysis

- What to investigate
  - Page timings
  - Referrers and bounce rates
  - referrers and time on page
    - quality metric 
  - exit rates vs bounce rates
  - content experiments
- Behavior > page timings
  - avg page load time
  - can search for specific pages
  - TODO: secondary dimension - page views
    - third column change to avg page load time 
      - to see pages with highest load times
      - go to speed suggestions and find individual pages
    - Add segment for mobile and tablet
    - Then compare all users vs mobile
- Referrer and bounce rate analysis
  - Acquisition > All traffic > Referrals
    - Sort by bounce rate
    - Add secondary dimension: landing page
      - optional: switch to pivot table
        - pivot metrics: select bounce rate
  - Acquisition > All traffic > Source/Medium
    - may want to export data to Excel and analyze with filters in spreadsheet
    - Sort by avg session duration
    - Select secondary dimension to landing page
    - From report click edit to see metrics and can save as custom report
- Exit page analysis
  - Behavior > Site content > Exit pages
  - consider relationship between page views and exits
  - create segment for users that haven't left within 5 seconds (i.e. didn't bounce)
- pay-per-click traffic analysis
  - measures AdWords traffic
- Content experiments
  - Behavior > experiments
  - Create experiment
  - Use goals set up for site as measurement
  - Specify how much of your traffic this applies to, how long the experiment will last for
  - Configure experiment with URL (page) variants
  - This creates code with experiment ID and key
  - Add code to the page

## Conversion reports

- Multi-channel funnel reports
  - track user across multiple channels
  - can see conversion path data
- Attribution models
  - Attribution > Model comparison tool
    - allows you to give credit to marketing efforts
    - Models
      - last interaction: attributes to last channel user interacts with
      - Non-direct click: last non-direct interaction
      - first interaction
        - can place premium on keywords or channels that were first exposure
      - linear: equally distributed
      - time decay: attributes more value to nearest channel of interaction
      - position based: weights first and last interactions higher
- Custom attribution models
  - Create default custom model
    - lookback model: specify time before
    - adjust credit
    - apply custom credit rules
