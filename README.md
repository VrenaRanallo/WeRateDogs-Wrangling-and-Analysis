# WeRateDogs-Wrangling-and-Analysis
Wrangling and Analysis from WeRateDogs.com

#### Gathering Data:

	The prompt for this report asked for three separate dataset that were gathered through three different methods. First, I manually downloaded the twitter_archive_enhanced.csv files that was provided and uploaded it to my notebook. The second file was housed on Udacity servers and so I used the Requests library to programmatically download it to my notebooks. The third and final data was gathered through Twitters API. I was unable to get the access needed through my own twitter account and needed to get access to the data through Udacity. 

#### Assessing Data: 

	I started my data assessment with a quick visual assessment. I could see that there were several columns with a lot of null values, there were inconsistencies in the capitalization of some columns, and a few dog names that were incorrectly labeled or missing. Then I turned my attention to the tidiness of the data. I recognized that there were 4 columns that were created to categorize the dog type, many of the columns that I notices null values were not relevant to the analysis I wanted to perform, and that all three files could be combined into one tidy data frame. 
	Once my quick visual assessment was done, I started to programmatically look at the data for additional issues with the data. I documented each issue I found as either a quality issue or a tidiness issue and moved onto cleaning the data. 


#### Cleaning Data:

	This step was of course where I spent most of my time and found the most challenging. I started by creating ‘clean’ copies of the data. I then isolated the retweets and removed them from the data, ensuring that I only had data with the original tweet.  I then addressed the missing data and found that I could remove most of the columns as they weren’t necessary for my analysis. 
	Once most of the missing data was addressed, I started to tidy the data. I created one column for the dog type and removed the 4 unnecessary columns (doggo, pupper, puppo, floofer). I changed the tweet_id’s to strings so I could use them to merge the dataset into one table. At this point I considered my data to by tidy and moved onto addressing the rest of the quality concerns. 
	In my assessment, the names I observed to be incorrect were all lower case, I replaced them with ‘None’. Then I wanted to standardize a rating system so I could run analysis on it. This made me take a closer look at the rating numerators and realized that if the text rating had a decimal the value in the data frame was incorrect. I created a for loop to search for ratings with a decimal, found 4 and replaced them with the correct values. Then I standardized the rating system by dividing the numerator and denominators and storing it in the ’total_rating’ column. 
	My final task was to address inconsistencies that came from the images data frame. I found and replaced all of the hyphens with underscores and put the predicted dog breeds as all lowercase. 
