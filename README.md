# Wallapop_WebScraping

To decrease the carbon footprint of the ESADE community, a group of faculty and staff have decided to promote sustainable modes of transport to get to campus. For those living in the Sant Cugat area, walking will probably be an option. For those living in Barcelona, a bicycle will probably make more sense. There are at least three different ways in which you can get to ESADE Sant Cugat from the city center: 

You can take a small, foldable bike with you in the train. FGC allows bikes to enter trains at all hours and there are bike hangers at the front and rear of every train.
Alternatively, you can also ride through Rabassada in a road bike. Might not be the best diea during rush hours, but it has the added benefit that you'll get to also explore the area during the weekends.
Finally, you can take a longer, wilder route through one of the mountain roads using a MTB. There's a shower at the basement level of the Sant Cugat building that you may want to use afterwards.

The objective of this assignment will be for you to look for second hand bikes available in Wallapop in the Barcelona area that fulfill the criteria above. For those of you who are not familiar with this website, Wallapop is a Spanish company founded in 2014 used to exchange used goods, similar to Craigslist as a classified listings website.


## Part  1

The goal of this part will be to retrieve information of search results in Wallapop for the three different options above.

1. Your code should initialize a Chrome web driver and access the Wallapop webpage
2. From here, it should use the searchbox to look for all results matching the keyword “bicicleta” (bike in Spanish)
3. Under the different search options provided, your code should only access those entries in the category “Bicicletas” (bikes in Spanish)
4. Filter the search results according to the following criteria:
Location. You should only retrieve results in “España, Barcelona” and narrow down the search to a maximum of “10km”
Price. Because you will probably be looking for second hand goods, limit the price to 800€.
Subfield. Within the “Bicicletas” field, there are multiple subfields available. Narrow down your search to include only results in the “Bicicletas y triciclos” subfield. 
Labels. You can further narrow down your search by choosing more refined subfields. You should retrieve only those results that correspond to “Bicicletas de carretera” (road bikes), “Bicicletas plegables” (foldable bikes) or “MTB” (mountain bikes).
State. You are only interested in bikes that are reasonably new. Hence, you should only include those results that correspond to bikes that are “Nuevo” (New), “Como nuevo” (As good as new) and “En buen estado” (In good condition).
5. Considering all the different combinations among the options above ("Bicicletas de carretera" and "Nuevo", "Bicicletas de carretera" and "En buen estado", etc.), retrieve the following information for all the available results (if less than 250) or for the first 250 results (if more than 250): Exclude all results corresponding to adds.
The URL address to the post
The URL address to the displayed image
The ti tle of the post
The price
The full description (as shown in the results page)
6. Store the retrieved information in a DataFrame called df under the following columns:
"Link" (in str form)
“Title” (in str/object form)
“Description” (in str/object form)
“Price” (in float form)
“Image” (in str/object form).


## Part 2

7. In addition to the above, include an additional column “Type” including a reference to whether the considered record corresponds to a “Bicicleta de carretera”, a “Bicicleta plegable” or “MTB”
8. Also include a column “State” to specify whether the considered bike is “Nuevo”, “Como nuevo” or “En buen estado”.
9. It is possible that the same result is included more than once in the different searches. To avoid redundancy, drop all the duplicates from your DataFrame
10. Include an additional column “Children” to identify whether the considered entry corresponds to a children bike or not. These should be identified by the keywords “niño/a”, “niño”, “niña”, “niños” , “niñas” or "niño/as", appearing either in the title or in the description of each result. Fill in the “Children” column with a boolean True whenever each of the provided keywords are present.
11. An important piece of information is the size of the bike. Not all search results will specify the size. When they do, make sure you retrieve these data and store them in a new column “Size” (in int form). The keyword for size in Spanish is “talla”. Note that bike sizes are usually along the ranges 54 - 60 approx.
12. Sometimes the size will be specified as S, M or L, When this happens, store the corresponding information in a new column called "Size (letter)"
13. Write the code to create a new dataframe called agg that includes the aggregated data for the "Type" and "State" columns. This Dataframe should include the average prices by "Type" and "State" (in this order)
