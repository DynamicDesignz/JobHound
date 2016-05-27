# JobHound
A web interface wrapper which leverages a lite version of PosAg to configure and scrape job listings from specific search URLs

# Dependencies
- Ruby >=v2.0.0
- Gems:
	- sinatra
	- launchy
	- nokogiri
	- sqlite3
	- chronic
- Modules:
	- open-uri
	- openssl
	- yaml
	- json

1. Run ```bundle install``` in the base directory to install any gem dependencies you may be missing

2. Run ```ruby jobhound.rb```. This will automatically start a local web server and navigate to http://localhost:4567 with JobHound running

3. Configure scraping sources by modifying ```config```:
	> - ```base_url``` - The base url for your scrape source. This is used for rebuilding partial urls.
	> - ```search_url``` - The specific search page you wish to scrape listings from.
	> - ```listing_url_regex``` - A regex pattern and replacement for the listing url during aggregation 
	> - ```date_posted_regex``` - A regex pattern and replacement for the date posted during aggregation 
	> - ```entry_css_path``` - The CSS selector for indivitual entries. All other paths are relative to this path.
	> - ```url_css_path``` - The CSS selector for the full listing URL relative to entry_css_path
	> - ```title_css_path``` - The CSS selector for the listing title relative to entry_css_path
	> - ```summary_css_path``` - The CSS selector for the listing summary relative to entry_css_path
	> - ```employer_css_path``` - The CSS selector for the listing employer relative to entry_css_path
	> - ```location_css_path``` - The CSS selector for the listing location relative to entry_css_path
	> - ```date_posted_css_path``` - The CSS selector for the listing post date relative to entry_css_path

4. Go to the "Jobs" page and hit the "Scrape Listings" button. This may take a minute depending on how many sources you are scraping from