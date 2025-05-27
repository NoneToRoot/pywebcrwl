# pywebcrwl

**pywebcrwl** is a simple Python web crawler that extracts various types of information such as links, emails, phone numbers, keywords, and more from websites.

## Features

- Crawl and extract all pages from a given URL
- Extract email addresses (with optional domain filtering)
- Extract phone numbers (including international formats)
- Detect cities mentioned in the text
- Find matches for a given regular expression
- Extract all image URLs
- Extract all websites/domains mentioned on a page
- Extract downloadable documents (optionally by file extension)
- Extract raw HTML code of pages
- Identify keywords from the content
- Extract all sentences containing a specific word
- Extract website favicons
- Extract social media links
- Generate a summary (resume) of a page

  ## Documentation
### `extract_emails(urls)`

Scans each URL in the `urls` list using a regular expression to find and extract valid email addresses from the page content.

> ⚠️ **Note**: Since the extraction is based on regular expressions, some results may include false positives.

**Parameters**:
- `urls` (`list`): A list of URLs to crawl and search for email addresses.

**Returns**:
- `list`: A list of all email addresses found on the provided URLs.


### `extract_pages_from_url(url)`

Crawls all internal links found on the given URL and returns a list of all pages discovered from that domain.


**Parameters**:
- `url` (`str`): The starting URL to begin crawling from.

**Returns**:
- `list`: A list of unique page URLs that were found during the crawl, including the original URL.




## Installation

```bash
pip install pywebcrwl
