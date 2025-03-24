# CeneoScraper

## Algorithm for  extracting opinions about single products from Ceneo.pl
1. send a request for accessing first webpage with opinions about products
2. If responce is ok, parse HTML page content into DOM structure 
3. Extract from DOM structure  opinions and their components
4. Assign opinions with their components to complex data structure
5. If there are more pages with opinions, repeat all steps 1-5
6. Save  data structures with opinions into  database

##Structure of  the simple opinion in ceneo.pl
|Component|Variable|Selector|
|---------|--------|--------|
|opinion|opinion|div.user-post__text|
|opinion ID|opinion_id||
|opinion’s author|author|span.user-post__author-name|
|author’s recommendation|recommend|<span class=user-post__author-recomendation>Polecam|
|score expressed in number of stars|stars|span.score-container score-container--s  js_score-container |
|opinion’s content|content||
|list of product advantages|pros||
|list of product disadvantages|cons||
|how many users think that opinion was helpful|up_votes||
|how many users think that opinion was unhelpful|down_votes||
|publishing date|published||
|purchase date|purchse||