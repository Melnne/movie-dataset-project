# movie-dataset-project

## Introduction
This analysis aims to derive meaningful insights from the TMDB (The Movie Database) dataset, focusing on various movie aspects such as genre distribution, temporal trends, geographical patterns, and key contributors in the film industry. Through data cleaning, exploratory data analysis (EDA), and visualization, the objective is to uncover patterns, trends, and relationships that can guide strategic decisions in content creation and distribution.


## Data Discription
The dataset provided contains information about various movies available on a streaming platform. The dataset includes details such as movie title, director, country, date added, release year, rating, duration, and genres 
 Data Dictionary:
- Show_id: Unique identifier for each show or movie.
- Type: Type of content (e.g., Movie, TV Show).
- Title: Title of the show or movie.
- Director: Director of the show or movie.
- Country: Country of origin.
- Date added: Date when the content was added to the streaming platform.
- Release year: The year the content was released.
- Rating: Content rating.
- Duration: Duration of the content.
Listed in: Categories or genres the content belongs to.

## METHODOLOGY
### Data Cleaning
#### Load the Dataset:
- Import essential libraries like pandas, NumPy, matplotlib, and seaborn.
- Load the dataset into a pandas DataFrame.
`import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv('/content/TMBD Movie Dataset.csv')
df`

#### Remove Duplicates and Unnecessary Columns:
- Identify and eliminate duplicate records. `df.duplicated().sum()`
- Drop irrelevant columns that won’t be used in the analysis (e.g., unamed).
`df.drop('Unnamed: 0', axis=1, inplace = True)`
  
#### Handle Missing Values:
- Detect columns with missing data. `df.isnull().sum()`
- Apply appropriate strategies to manage missing values, such as filling with the mean/median or removing rows.
  
#### Ensure Data Type Consistency:
- Ensure columns have the correct data types 
- Convert date columns to datetime format. `df.loc[:, 'release_date'] = pd.to_datetime(df['release_date'], format='YOUR_DATE_FORMAT', errors='coerce')`
	
## Exploratory Data Analysis (EDA):
### Summary Statistics:
- Compute basic summary statistics for numerical columns (mean, median, min, max).
- Explore the distribution of release years, durations, and ratings.
### Categorical Variables:
- Analyze the distribution of show types (Movies vs. TV Shows).
- Explore the diversity of countries, directors, and genres.
### Temporal Trends:
- Examine how the number of shows/movies has changed over the years.
- Identify any patterns in the date-added column.
### Correlation Analysis:
Use scatter plots or correlation matrices to explore relationships between variables such as  revenue.

## Visualization Techniques
Histograms:
•	Show the frequency distribution of release years and movie runtimes.
Bar Charts:
•	Illustrate the distribution of movie and highlight top genres or directors.
Line Charts:
•	Depict trends over time, such as the number of movie releases per year and per month
Scatter Plots:
•	Explore relationships between numerical variables like revenue and popularity.

### Key Findings:
Distribution Of Release Years
The dataset spans 54 years of movie data, covering a wide range of genres.  Movie releases experienced a gradual increase, reaching a peak in 2011 with 156 movies released, after which a period of decline was observed.

![Release](https://github.com/user-attachments/assets/48067025-27d9-4b3d-aebb-1888007e4620)


## Distribution Of Durations
The average runtime of movies in the dataset is 110.26 minutes. The longest movie is The Lord of the Rings: The Return of the King at 201 minutes, while the shortest is Winnie the Pooh at 63 minutes. As observed on the chart most movies have a runtime between 90 and 110 minutes, with a peak frequency in the 100-minute bin. Very few movies exceed 150 minutes.
There is a moderate correlation between runtime and revenue, with movies lasting between 90 and 140 minutes generating the highest revenue. A possible reason for this trend is that movies with runtimes between 90 and 140 minutes tend to strike a balance between keeping audiences engaged and providing sufficient time for plot and character development making them more appealing to a wider audience.

![Duration](https://github.com/user-attachments/assets/6bba7469-dcf9-4125-a934-67eef67306d2)


## Distribution Of RATINGS
The average movie rating is 6.28. The highest-rated film is The Godfather with a score of 8.3, while the lowest-rated is Foodfight with a rating of 2.2.
Furthermore, there appears to be a relationship between movie popularity and ratings. 

![Relationship](https://github.com/user-attachments/assets/719857b0-ef29-4d71-a1d7-33adc6621b69) ![Relationship 2](https://github.com/user-attachments/assets/53a7e9ea-f332-4d28-8d6f-f73fa60b4143)

As observed in the chart, more popular movies tend to receive higher ratings compared to less popular ones. This could be attributed to the fact that widely discussed and viewed movies often garner greater appreciation from audiences, leading to higher ratings. And also there is a noticeable relationship between popularity and revenue, this goes to say that the more popular a movie is the more revenue it will most likely generate.




## DIVERSITY OF DIRECTORS

![Directors](https://github.com/user-attachments/assets/a121b4b7-a5f3-404e-a357-1edcff8e3db0)



![Director 2](https://github.com/user-attachments/assets/b79e0fef-2fc4-42af-ab8e-576f806d8484)



![Director 3](https://github.com/user-attachments/assets/ba6e9040-9d5b-4f36-bf0c-390c57e5cc1c)

John Carpenter is the most prolific director in the dataset, with 12 films. Despite directing fewer movies (8), Peter Jackson generated the most revenue and ranks as the second most popular director, just behind Christopher Nolan, the most popular. Peter Jackson stands out as a top-performing director, consistently producing both financially successful and popular films.

## Diversity Of  Genres
![Genre](https://github.com/user-attachments/assets/b83b72d9-37d6-4532-a238-7ea09b7b4c69)

The dataset includes 535 Drama movies, 414 Action movies, 414 Comedy movies, 399 Thrillers, 297 Adventure, 209 Science Fiction, 196 Romance, 193 Crime, 163 Family, 154 Fantasy, 139 Horror, 108 Animation, 98 Mystery, 38 Music, 35 History, 31 War, 15 Documentaries, 13 Westerns, and 1 Foreign film.
In terms of revenue, the ‘Adventure|Fantasy|Action’ genre combination leads with a total of $7.43 billion, followed by Comedy at $6.87 billion and Drama at $6.57 billion. On the other hand, the ‘Crime|Drama|Mystery|Thriller’ combination generated the least revenue at just $7,306, which is significantly below the average revenue of $176.33 million across all genres.
Adventure|Fantasy|Action had the highest profit with 5.86 billion, while Adventure|Fantasy|Action|Western|Thriller had the least profit with a total of -413912431.0 billion
In terms of popularity, Drama is the most popular genre, scoring 84.85, with Comedy close behind at 81.68. The least popular genre is ‘Crime|Drama|Mystery|Thriller,’ with a popularity score of 7.306.



## How The Number Of Movies Has Changed Over The Years

![movie](https://github.com/user-attachments/assets/1f069059-716d-448a-bb55-755275b6f9c6)

From 1960 to 1969, only 8 movie was released. The number gradually increased in the following decades, with 19 movies released between 1970 and 1979, and 33 movies in the 1980s. The 1990s saw a significant rise with 85 movies, followed by a sharp increase to 538 movies in the 2000s. The period from 2010 to 2015 reached the highest point, with 603 movies released.

![movie 3](https://github.com/user-attachments/assets/bdcf0a99-cc4c-4a61-8955-11562213c1e3)

September has the highest number of movie releases (169), followed by December (131). January and February see the fewest releases, with 76 and 77 respectively, suggesting that producers might be strategically aiming for the holiday season and increased Christmas viewership.

![movie 4](https://github.com/user-attachments/assets/c83928de-8fe8-4fee-a0b1-fe5de68b64b4)

June and December are the most profitable months, exceeding $2.4billion and $2.2 billion in profit, respectively. July, May, and November also perform well, with profits ranging from $1.5 billion to $1.8 billion. January, February, and August see the lowest profits, each falling below $1 billion.
Friday is the most common day for movie releases, likely a strategic choice to capture weekend audiences as people unwind from the workweek.

![movie 5](https://github.com/user-attachments/assets/1a431d49-2008-4b7d-9b59-8a11348bfca2)


