# Movie Recommenders in Python

For getting the results I've used movielens datasets.

### Reading ratings

For loading the dataset I used pandas library with tab separator as given in the data. If
dates are specified we split the string into three elements: day, month, and year. After
that, we just filter dates that are between those two dates. For the number of minimum
ratings, we group the data frame by each movie to get how many ratings each movie has
received.

### Reading movies

Load the movie dataset but with "ISO-8859-1" encoding specified since some of the characters in the dataset could not be read by UTF-8

### Random predictor

In this class, we are using the random library to generate an array of random values for
each movie in the dataset. After we gather it, we save the index of the movieID and the
rating from the predictor. Since we are taking random values, results are different every
time we run the method.

### Recommendation

Recommender class takes another class in the constructor for which we can use the
fit method to save the data frame. Since the predict method has the option of whether
the user wants to see the movies that are already rated, we had to filter the movies and
delete that from the result dictionary. When getting the result, we just had to sort and
show the movies which are rated with the highest score.

### Average predictor

Firstly we group by movieID, sum ratings for each movie and use the size to calculate
each score. After that, we push each score into the dictionary which we return. Results
were the same as we had in the instructions.

### Recommending the most watched movies

Views Predictor class will return dictionary as well but here I’ve used operator library to
reverse sort the dictionary. The results were somewhat different and the movie Matrix
had the most reviews.

### Predicting scores with similarity between products

For item-based recommendations, I’ve used a few helper libraries, NumPy to easily
compute norm in cosine distance equation, and itertools and operator for dealing with
dictionaries. When calculating the similarity the main thing was to find the intersection
of movie parameters and getting the ratings. After acquiring ratings we can just calculate
the dot product between those ratings and divide it with norms. In the predict method,
we use the similarity to calculate the similarity between each movie, save it and reuse it
in the prediction formula. The results were kind of weird but I checked some of them
manually and they were the same.

### Most similar movies

The execution of this method was pretty lengthy, and the results were kind of similar
because of the movies but the cosine distance was higher than given in the instructions.
The idea was quite simple, just two for loops and a reverse sorted dictionary where it is
all saved.

### Recommendation based on the currently viewed content

This method is similar to the previous one, just this time we find the similarities for only
one movie, and in this case, as well we received similar results in terms of movies but
the distance was a little higher.

### Recommendation for yourself

I’ve manually entered the rows in the data frame with the append function from the
pandas library. For the results I’ve received some great suggestions:
Movie: Fargo, score: 4.202642547257465
Movie: Reservoir Dogs, score: 4.202600207301209
Movie: Wo hu cang long, score: 4.202534492030078
Movie: Monty Python and the Holy Grail, score: 4.20245748575363
Movie: Blade Runner, score: 4.202368604369937

### Prediction with Slope One method

The prediction for this method had a pretty lengthy process as well, as it has a lot of
computations to perform. In my case, I first find the intersection of the two users, find
the deviation and save it to the dictionary, then use the results from that dictionary to
find a prediction for each movie. I had slightly different results from the instructions, but
considering the movies that were given, I think they were quite good recommendations.
