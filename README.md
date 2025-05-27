# pywebcrwl

**pywebcrwl** is a simple Python web crawler that extracts various types of information such as links, emails, phone numbers, keywords, and more from websites.

 ***DISCLAIMER***: ddd

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
- `urls` (`list`): A list of URLs to crawl and search for email addresses. Each URL MUST start by "https://" following by the remaining part of the URL.
  
Example : "https://example.com" or "https://www.example.com"

**Returns**:
- `list`: A list of all email addresses found on the provided URLs.

**Example**

```python
import pywebcrwl

list_of_emails = pywebcrwl.extract_emails(['https://exemple.com'])
print(list_of_emails)
 # [exemple1@gmail.com, exemple2@exemple.com,...]
```
----------------------------------------------------------------------------------------------------------------------------------------------------

### `extract_pages_from_url(url)`

Searches all internal links on the given website URL and returns a list of all pages found from the same domain.

**Parameters**:
- `url` (`str`): The starting URL to begin searching from. The URL MUST start by "https://" following by the remaining part of the URL.
  
Example : "https://example.com" or "https://www.example.com"

**Returns**:
- `list`: A list of all page URLs that were found during the crawl, including the original URL.

**Example**

```python
import pywebcrwl

list_of_pages = pywebcrwl.extract_pages_from_url('https://example.com')
print(list_of_pages)
# [https://example.com, https://example.com/docs, https://example.com/img, https://example.com/img/picture, ...]
```
----------------------------------------------------------------------------------------------------------------------------------------------------

### `extract_by_regex(urls, regex)`

Searches in the HTML content of each URL for all matches of a given regular expression.

**Parameters**:
- `urls` (`list`): A list of URLs to search in and scan.
- `regex` (`str`): A regular expression pattern used to search inside the page text.

**Returns**:
- `list`: A list of all unique matches found across the given URLs.

**Note**:
- Results depend entirely on the quality and accuracy of the regular expression you provide.

**Example**:

```python
import pywebcrwl

# Pattern for dates like 27/05/2025 or 27-05-2025
pattern = r"\b\d{2}[/-]\d{2}[/-]\d{4}\b"
matches = pywebcrwl.extract_by_regex(["https://example.com"], pattern)
print(matches)
# [24-05-2020, 12-09-2024, 01/05/2021, ...]
```

----------------------------------------------------------------------------------------------------------------------------------------------------

### `extract_emails_by_domain(urls, domain)`

Searches all given URLs and extracts email addresses that match a specific domain (like `gmail.com` or `mycompany.org`).

**Parameters**:
- `urls` (`list`): A list of website links (URLs) to visit and check.
- `domain` (`str`): The email domain you are looking for (for example: `"example.com"`).

**Returns**:
- `list`: A list of email addresses that use the given domain name.

**Example**:

```python
import pywebcrwl

emails = pywebcrwl.extract_emails_by_domain(["https://example.com"],"example.com")
print(emails)
# [123@exemple.com, CEO@example.com, john@example.com, ... ]
```

----------------------------------------------------------------------------------------------------------------------------------------------------


















## Installation

```bash
pip install pywebcrwl
