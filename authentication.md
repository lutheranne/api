ArtFacts.Net API: Authentication
================================

You must be authenticated to use the ArtFacts.Net API. 

Authentication is provided by [HTTP Basic Access Authentication](http://en.wikipedia.org/wiki/Basic_access_authentication) with the security of data transmission provided via HTTPS.

You will be provided with your authentication credentials when you create your ArtFacts.Net API account.

## Example Connection

Below are some example connections using **curl**.

This API request gets the top 10 ranking artists. Valid authentication credentials are supplied

    curl -u valid-user:password https://api.artfacts.net/v1/ranking/top?limit=10

Example response from above request

```json
[{"ArtistID":"328","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/328\/lang\/1","Name":"Andy","Surname":"Warhol","Nationality":"US","BirthDates":"1928-1987","Rank":"1","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"627","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/627\/lang\/1","Name":"Pablo","Surname":"Picasso","Nationality":"ES","BirthDates":"1881-1973","Rank":"2","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"3205","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/3205\/lang\/1","Name":"Bruce","Surname":"Nauman","Nationality":"US","BirthDates":"1941","Rank":"3","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"516","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/516\/lang\/1","Name":"Joseph","Surname":"Beuys","Nationality":"DE","BirthDates":"1921-1986","Rank":"4","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"1060","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/1060\/lang\/1","Name":"Gerhard","Surname":"Richter","Nationality":"DE","BirthDates":"1932","Rank":"5","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"959","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/959\/lang\/1","Name":"Sol","Surname":"LeWitt","Nationality":"US","BirthDates":"1928-2007","Rank":"6","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"1832","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/1832\/lang\/1","Name":"John","Surname":"Baldessari","Nationality":"US","BirthDates":"1931","Rank":"7","3y_slope":"-1","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"2789","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/2789\/lang\/1","Name":"Cindy","Surname":"Sherman","Nationality":"US","BirthDates":"1954","Rank":"8","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"2298","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/2298\/lang\/1","Name":"Ed","Surname":"Ruscha","Nationality":"US","BirthDates":"1937","Rank":"9","3y_slope":"0","RankingDate":"2013-02-09","MergedIDs":null},{"ArtistID":"971","link":"http:\/\/www.artfacts.net\/index.php\/pageType\/artistInfo\/artist\/971\/lang\/1","Name":"Lawrence","Surname":"Weiner","Nationality":"US","BirthDates":"1942","Rank":"10","3y_slope":"-1","RankingDate":"2013-02-09","MergedIDs":null}]
```

The same request as above, but this time with invalid authentication credentials (this time we've added the `-i` switch to the curl command to output the headers)

    curl -i -u invalid-user:incorrect https://api.artfacts.net/v1/ranking/top?limit=10

The response (with truncated headers)

    HTTP/1.1 401 Unauthorized
    Date: Mon, 25 Mar 2013 21:34:59 GMT
    Content-Type: application/json
    Transfer-Encoding: chunked
    Connection: keep-alive
    
    {'error': 'You are not authorized to view this page'}

----
* [index](README.md)
* [authentication](authentication.md)
* [end points](endpoints.md)
