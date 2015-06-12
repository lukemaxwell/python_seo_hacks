
## Download Sitemap URLs

    from lxml import etree 

    def download_sitemap_urls(sitemap_url):
        # Parse remote sitemap
        tree = etree.parse(sitemap_url)
        # Extract namespace
        ns = tree.getroot().nsmap[None]
        # Extract URLs using xpath and namespace
        urls = tree.xpath('/s:urlset/s:url/s:loc/text()', 
            namespaces={'s': ns})

        return urls

## Write to csv
	import csv

	# data is a list of lists [[]]
	def write_to_csv(filename, data)
		with open(filename, 'w') as f:
			csv_export = csv.writer(f)
			csv_data = []
			for row in data:
				csv_row = [item.encode("utf-8")
					if isinstance(item, unicode) else str(item)
					for item in row]

				csv_data.append(row)

			csv_export.writerows(csv_data)
			return True

		return False

## Create sitemap
## Write to Excel
## Write to Google Spreadsheet
## Check robots.txt
## Bulk robots.txt checker
## Google Webmaster Tools crawl errors
## Find proxies
## Test proxies
## Search Twitter
	from twitter import *
	import json
	consumer_key = 'Bm6HALfQPWJmnLATt8PGQu1pF'
	consumer_secret = 	'avoFUUhHD9OZ4PJga9nK9AKqIkV3C8XxO06xGKf65ocVDX0zJw'
	access_token = '373618025-					E662cyYTBNDECgYelj4MZR9Gff6E6gSjohTeqGZe'
	access_token_secret = 	'GOAhvgzOuRQkVo6v1DXLr1PHTZUjbVmCQwgV8Ch8srCrM'
	twitter_api = Twitter(auth=OAuth(access_token, 		access_token_secret, consumer_key, consumer_secret))
	WORLD_WOE_ID = 1
	US_WOE_ID = 23424977
	#world_trends = api.trends.place(_id=WORLD_WOE_ID)
	#us_trends = api.trends.place(_id=US_WOE_ID)
	#print world_trends
	#print
	#print us_trends
	q = '#seo'
	count = 100
	search_results = twitter_api.search.tweets(q=q, 		count=count)
	statuses = search_results['statuses']

	Iterate through 5 more batches of results by following the cursor

	for _ in range(10):
		print "Length of statuses", len(statuses)
		try:
			next_results = search_results['search_metadata']['next_results']
		except KeyError, e: # No more results when next_results doesn't exist
			break

	Create a dictionary from next_results, which has the following form:
		# ?max_id=313519052523986943&q=NCAA&include_entities=1
		kwargs = dict([ kv.split('=') for kv in next_results[1:].split("&") ])

    search_results = twitter_api.search.tweets(**kwargs)
    statuses += search_results['statuses']

	# Show one sample search result by slicing the list...
	print json.dumps(statuses[0], indent=1)

## Get data from Google Analytics
## Check website is up
## Get domain information
## Harvest email addresses (Warning)
## Get Moz metrics
## Analyse Logs for Google Bots
## Duplication Test (supplementary index)
## Get Adwords data
## Send emails with gmail
## Create a spider
## Crawl a website
## On-Page SEO Checker