[![Web Scraping Logo](https://cfe2-static.s3-us-west-2.amazonaws.com/media/courses/web-scraping/images/Web-Scraping.jpg)](https://www.codingforentrepreneurs.com/courses/web-scraping/)

Learn how to leverage Python's amazing tools to scrape data from other websites.

The end goal of this course is to scrape blogs to analyze trending keywords and phrases.

We'll be using Python 3.6, Requests, BeautifulSoup, Asyncio, Pandas, Numpy, and more!

## Section 1: [Scraping Top Repositories for Topics on GitHub](https://www.codingforentrepreneurs.com/courses/web-scraping/your-first-scraping-program/)
Watch [here](https://www.codingforentrepreneurs.com/courses/web-scraping/your-first-scraping-program/)

Web scraping is the process of extracting and parsing data from websites in an automated fashion using a computer program. It's a useful technique for creating datasets for research and learning. Follow these steps to build a web scraping project from scratch using Python and its ecosystem of libraries:

#### Install Guides
Windows: https://kirr.co/6r8wr9

Mac: https://kirr.co/386c7f

Linux: https://kirr.co/c3uvuu

#### Goals of Your First Scraping Program:

1. Enter any url (webpage)
2. Open and scrape that webpage's words each word
3. Save that info into a csv

###### TODO (Intro):

- Python Requests : http://docs.python-requests.org/en/master/Introduction about web scraping
- Introduction about GitHub and the problem statement
- Mention the tools you're using (Python, requests, Beautiful Soup, Pandas)

    ```
    pip install requests
    ```
    Basically, it opens the webpage for us in this one.

- BeautifulSoup 4 : https://www.crummy.com/software/BeautifulSoup/bs4/doc/

    ```
    pip install beautifulsoup4
    ```
    This allows us to search & extract content from an HTML webpage






## Section 2: [Advancing Scraping](https://www.codingforentrepreneurs.com/courses/web-scraping/advancing-scraping/)


#### Goals of Advancing Scraping:
1. Refine scraping code
2. Scrape Links
3. Add Scrape Depth
4. Scrape & Parse words in a Post


#### Here are the steps we'll follow:

- We're going to scrape https://github.com/topics
- We'll get a list of topics. For each topic, we'll get topic title, topic page URL and topic description
- For each topic, we'll get the top 25 repositories in the topic from the topic page
- For each repository, we'll grab the repo name, username, stars and repo URL
- For each topic we'll create a CSV file in the following format:
- Repo Name,Username,Stars,Repo URL
- three.js,mrdoob,69700,https://github.com/mrdoob/three.js
- libgdx,libgdx,18300,https://github.com/libgdx/libgdx

#### Scrape the list of topics from Github
Explain how you'll do it.

- use requests to downlaod the page
- user BS4 to parse and extract information
- convert to a Pandas dataframe
Let's write a function to download the page.

    ```
   import requests
from bs4 import BeautifulSoup

def get_topics_page():
    # TODO - add comments
    topics_url = 'https://github.com/topics'
    response = requests.get(topics_url)
    if response.status_code != 200:
        raise Exception('Failed to load page {}'.format(topic_url))
    doc = BeautifulSoup(response.text, 'html.parser')
    return doc
    ```
    Add some explanation
    
    ```
    doc = get_topics_page()
    ```
    Let's create some helper functions to parse information from the page.

- To get topic titles, we can pick p tags with the class ...

   ```
   def get_topic_titles(doc):
    selection_class = 'f3 lh-condensed mb-0 mt-1 Link--primary'
    topic_title_tags = doc.find_all('p', {'class': selection_class})
    topic_titles = []
    for tag in topic_title_tags:
        topic_titles.append(tag.text)
    return topic_titles
    ```
   


Web scraping is the process of extracting and parsing data from websites in an automated fashion using a computer program. It's a useful technique for creating datasets for research and learning. Follow these steps to build a web scraping project from scratch using Python and its ecosystem of libraries:

### Pick a website and describe your objective

- Browse through different sites and pick on to scrape. Check the "Project Ideas" section for inspiration.
- Identify the information you'd like to scrape from the site. Decide the format of the output CSV file.
- Summarize your project idea and outline your strategy in a Juptyer notebook. Use the "New" button above.
### Use the requests library to download web pages

- Inspect the website's HTML source and identify the right URLs to download.
- Download and save web pages locally using the requests library.
- Create a function to automate downloading for different topics/search queries.
- Use Beautiful Soup to parse and extract information

### Parse and explore the structure of downloaded web pages using Beautiful soup.
- Use the right properties and methods to extract the required information.
- Create functions to extract from the page into lists and dictionaries.
- (Optional) Use a REST API to acquire additional information if required.
### Create CSV file(s) with the extracted information

- Create functions for the end-to-end process of downloading, parsing, and saving CSVs.
- Execute the function with different inputs to create a dataset of CSV files.
- Verify the information in the CSV files by reading them back using Pandas.
### Document and share your work

Add proper headings and documentation in your Jupyter notebook.
(Optional) Write a blog post about your project and share it online.
#### Notes

Use the "New" button on Jovian to create a new notebook, and select "Run on Binder" to get started.


