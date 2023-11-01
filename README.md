
# AN ANALYSIS TO INVESTIGATE THE KIND OF MOVIES THAT ARE PERFORMING WELL AT THE BOX OFFICE IN TERMS OF RATINGS, FOREIGN GROSS AND INSIGHTS.

### Business Understanding

Microsoft sees all the big companies creating original video content and they want to get in on the fun. They have decided to create a new movie studio, but they don’t know anything about creating movies. I am therefore charged with exploring what types of films are currently doing the best at the box office and then translate those findings into actionable insights that the head of Microsoft's new movie studio can use to help decide what type of films to create.

### Problem Statement

Microsoft stakeholders and top management are finding it hard understanding the specific movies that are performing well in terms of ratings, foreign gross, insights such as number of votes and genres that performed well. Without understanding these metrics it will be hard for them to create original video content through their movie studio. They are not sure where to start in order to investigate these metrics.

### Project's goal

Therefore this project is focused on investigating the above metrics inorder to come up with a decisive action to enable the microsoft studio to create only movies that are going to perform well internationally and be a good investment plan. Only the kind of movies that attract great insights through high number of votes, high foreign gross and higher ratings will be prioritised in the production studio.


### Data Understanding

In this analysis I used three different datasets which are from Box office Mojo, IMDB SQLite Database and The movie Database.
The datasets will be cleaned before performing exploratory data analysis. The datasets were chosen since they have data on foreign gross, domestic gross, genres, insights through number of votes the movies attracted and the movie ratings.
This will present a clear picture of how different movies performed and thus lead to the stakeholders and top management at Microsoft making informed decisions before production at the new movie studio.

### 1. BOX OFFICE MOJO DATASET
I will first start by reading the dataset inorder to understand the data and the kind of measurements that I will use to determine the success of movies


#### Size of the dataset

The above dataset has 3387 rows and 5 columns


### Checking for missing values

Missing values can occur for a variety of reasons, including measurement error, data entry errors and non-response.
The presence of missing data can cause biased estimates, inaccurate results, misleading visualisations as well as a loss of information.
By checking, identifying and addressing missing values before analysis, I will be able to increase the accuracy and reliability of my results



### Filling missing values in domestic_gross with its mean

This column cannot be dropped as it is of great significance as a metric for movie perfomance in terms of gross revenue.
Therefore missing values will be filled with the mean of domestic_gross


# domestic_gross has 0 missing values after filling with mean


### Addressing missing values in foreign_gross
For foreign gross I made an assumption that the missing values are as a result of the movies having 0 international sales
This might have been due to no international releases for those movies that have missing values
Therefore the best strategy was to fill with 0s since this column is vital in the analysis and cannot be dropped


# There are no missing values in the dataframe now

### Checking for duplicates in the data

By identifying and removing duplicates, I want to ensure that each observation in the Box office Mojo dataset is represented only once.
This will help to ensure data accuracy, efficiency, and consistency, and thus help in obtaining reliable and meaningful insights from the data.



### Identfying top 20 movies with high foreign gross



# Identifying the relationship between foreign gross and domestic gross

 Creating a scatter plot



### 2. IMDB SQLITE DATABASE

In this Database with several tables, I picked only two tables; movie_ratings and movie_basics which contain valuable data such as average rating and number of votes which will be used as metrics of movie perfomance.

I will join the two tables into one using the key "movie_id" which uniquely identifies the movies.
Everything from the two tables will be selected and start filtering on irrelevant data and columns.


### Dropping duplicating and irrelevant columns

In this dataframe that I have obtained from an SQLite database, movie_id columns appears twice and thus the need to drop one or even both since they are not that significant in my analysis.

My columns of interest are the averagerating and numvotes which will be used as metrics for movie perfomance


#### Decision made

Runtime_minutes has a total of 7620 missing values and genres 804 missing values. Runtime minutes will be dropped since there is no much use in this analysis and genres will be kept since it will enable me to understand the kind of movie genres that perfomed well.



### 3. THE MOVIE DATABASE

This dataset will be important in obtaining data for movie popularity, vote average and the vote count of different movies which will be vital in the analysis

tmdb_df=pd.read_csv("zippedData/tmdb.movies.csv.gz", index_col=0)
#index_col=0 was used to avoid having two index columns

tmdb_df

#### Size of the the movie database

The dataframe has 26517 rows and 9 columns

#The next step will be dropping unnecessary columns by creating a list of unnecessary columns
unnecessary_cols=["genre_ids","id","original_language","original_title","release_date"]




##### DISCUSSION

There is a low positive correlation between popularity and vote count of movies

### MERGING THE DATASETS

The three datasets will then be merged for Exploratory Data Analysis to take place.
Merging the datasets is vital since data will be combined from different sources to gain a more concise and complete information.
It will also increase the sample size thus improving the accuracy and reliability of my analysis.



### FINDINGS AND CONCLUSIONS

Different observations were noted when perfoming exploratory data analysis. These findings are explained below;

1. It was observed there was low positive correlation between domestic gross and foreign gross, which meant there little relationship between the two. 
Movies released between 2011 to 2018 earned the highest foreign gross. 


2. While analysing the top 15 genres with top number of votes received, it was observed that Action, Adventure, Sci-fi, Thriller, Drama, Comedy and Crime attracted a lot of insights from different people who voted.


3. While analysis top 10 popular movies, it was observed that sci-fi and action movies were the most popular, with Avengers: Infinity war topping with 80.773% popularity followed closely by John Wick with 78.123% and Spider Man: Into the spider verse with 60.534% popularity.


4. The final observation was that there was low positive correlation between number of votes and average rating of movies.

### RECOMMENDATIONS

Different recommendations were derived from the findings;

1.) It would be imperative for the stakeholders and top management at Microsoft to prioritise production of movies similar to those released between the year 2011 and 2018 since they earned the highest foreign gross. The top four earners included;
 a) Harry potter and the deathly hallows part 2 (2011)

 b) Avengers: Age of Ultron (2015)

 c) Marvel's The Avengers (2012)

 d) Jurrasic World: Fallen Kingdom (2018)

Since the top four earners were all Sci-fi movies, then Microsoft would have a great return on investment by creating Sci-Fi movies.

Foreign gross would lead to higher international sales. Higher foreign gross means there is also higher domestic sales, but higher domestic gross does not equate to higher foreign gross since from the scatter plot there is low positive relationship between the two variables.



2.) For Microsoft studio to create awareness of their existence and new products, it is recommended they focus more on Sci-Fi, Action, Adventure, Thriller, Drama, Crime and Comedy since they attracted the most votes from movie fans leading to high insights.



3.) For Microsoft to gain popularity and return on investments they should prioritise Sci-fi and Action movies such as Avengers: Infinity war topping with 80.773% popularity, John Wick with 78.123% and Spider Man: Into the spider verse with 60.534% popularity. 
This would ensure that the created movies at Microsoft studio attract great popularity leading to high international sales.
