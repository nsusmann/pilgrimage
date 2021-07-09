# pilgrimage
I created this script to scrape Trip Advisor "Things to Do" reviews from various tourist locations in Greece. The Monastery of Saint John the Theologian on Patmos Island is the default URL but you change this.

# Set up:
  1. Install Python 3.9
  2. Download get-pip.py: https://pip.pypa.io/en/stable/installing/
  3. Save the file in your Python 3.9 folder.
  4. Open cmd (command prompt) on your computer
  5. Point command prompt to the Python folder: 
        CD  C:\Users\nsusm\AppData\Local\Programs\Python\Python39\python get-pip.py
         *You should see a successful install message.
  6. Check installation:
        C:\Users\nsusm\AppData\Local\Programs\Python\Python39>pip
        *You should see the Pip menu
  7. Install Selenium:
        C:\Users\nsusm\AppData\Local\Programs\Python\Python39\Scripts\pip.exe install selenium
        *Get successful installation message
 
 # Get drivers:
 This script is designed to open up an internet browser, navigate to the review page and extract the review data. This means it's going to  click through "next page" multiple times. You need a webdriver for this to work.
   1. Choose and download your driver. Place it in either your Python or working folder Selenium shows options here:
       *Script is written to work with Chrome    
   2. If you selected a different driver:
       1) line 23: delete "Chrome" and select from the dropdown menu. Replace the file path with your driver location

#  FYI:
    1. line 7: pathway to store your csv output
    2. lines 13 + 14 + 24: url for the review
    3. line 30: tells Python what to name each header. These need to match the datasets you create (lines 42 - 46) and the data you     tell it to write (lines 49). 
    
 # How to change what data is scraped:
    The script is going to read the HTML code of the website and hone into certain fields that you create. For example:
    line 42: "rating" is an attribute I created representing the rating (x/5) on trip advisor. I opened up the URL of the review           website, right clicked and selected "inspect". I read through the html and found the specific xpath representing the rating and         inserted it into the code. I highly recommend this article for further explanations on how to do this:            https://www.edureka.co/blog/xpath-in-selenium/
    I repeated this process for each of the elements I wanted to scrape: review, date of review, reviewer name, reviewer title, and the review text. Notice that the name I made for the dataset (e.g. "rating" on line 42) matches 1) the respective heading on the csv Selenium will create (line 30) as well as when it writes to the csv (line 49). 
    
  # Troubleshoot
     1. If you've downloaded Selenium but get a "not found" error, make sure you're running the script in 3.9.6, or whichever version of Python you've installed Selenium in. 
     2. If you csv is empty, you need to close everything (Python, etc.) and it will write
     3. You might get an error screen about usb connections. You can ignore that if the script is still working (you'll know because the browser window will auto scroll). 
