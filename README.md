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
|opinion|opinion|div.user-post__text|div.user-post user-post__card js_product-review:not(.user-post--highlights)|
|opinion ID|opinion_id|  div.user-post user-post__card js_product-review["data-entry-id"]|
|opinion’s author|author|span.user-post__author-name|
|author’s recommendation|recommend|span.user-post__author-recomendation> em|
|score expressed in number of stars|stars|span.user-post__score.count |
|opinion’s content|content|div.user-post__text|
|list of product advantages|pros|div.review-feature__item--positive|
|list of product disadvantages|cons|div.review-feature__item--negative|
|how many users think that opinion was helpful|up_votes|button.vote-yes["data-total-vote"]|
|how many users think that opinion was unhelpful|down_votes|button.vote-no["data-total-vote"]|
|publishing date|published|span.user-post_published >  time:nth-child(1)["datatime"]|
|purchase date|purchse|span.user-post_published >  time:nth-child(2)["datatime"]|