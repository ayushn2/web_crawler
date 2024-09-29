# Web Crawler

This is a simple, recursive web crawler written in Go. The crawler starts at a given URL, downloads the HTML page, and extracts all hyperlinks from the page, printing them along with their text content and depth. It follows links up to a defined depth limit (`MaxDepth`).

## Features

- Recursively download web pages and extract hyperlinks (`<a>` tags).
- Limits recursion depth to avoid infinite crawling (default depth: 2).
- Filters out invalid links (e.g., `javascript:` links).
- Prints links in a hierarchical format to show depth.

## Getting Started

### Prerequisites

- Go 1.16 or higher.
- A working internet connection for downloading web pages.

### Installation

1. Clone the repository:
   ```bash
   git clone git@github.com:yourusername/web_crawler.git
   cd web_crawler

2.	Install dependencies (uses loglevel and golang.org/x/net/html):
    ```bash
    go get -u github.com/llimllib/loglevel
    go get -u golang.org/x/net/html

### Usage

- To run the crawler, pass a URL as an argument:

    ```bash
    go run main.go http://example.com

- This will:

	1.	Download the page at the given URL.
	2.	Extract all hyperlinks (<a> tags) and print them.
	3.	Recursively follow the links, up to the defined maximum depth (MaxDepth).

### Command-Line Arguments

-	URL: The starting URL for the crawler.
-	MaxDepth: The maximum depth to crawl (default is 2).

- Example Output

    ```bash
    Page Title (0) - http://example.com
    Link Text 1 (1) - http://example.com/link1
    Link Text 2 (1) - http://example.com/link2
        Sub Link Text (2) - http://example.com/sublink