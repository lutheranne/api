ArtFacts.Net API: End Points
==================

In **Version 0** of the ArtFacts.Net API there are relatively few request endpoints, all of which are outlined on this page.

----

## End Points

- [Top Ranking](#top-ranking) `GET /v0/ranking/top/`
- [Up and Coming](#up-and-coming) `GET /v0/ranking/upandcoming/`
- [Artist Search](#artist-search) `GET /v0/artist/search/<search+criteria>/`
- [Artist Details](#artist-details) `GET /v0/artist/<ID>/`

----

## Top Ranking


Gets the top list of artists based on the ArtFacts Ranking.

    GET /v0/ranking/top/

### Parameters

-   **limit** - *int* (optional) - number of artists to return
    -   min = 1
    -   max = 1000
-   **offset** - *int* (optional) - start the artist returned from this ranking number
    -   min = 1
-   **nationality** - *string* (optional) - filter returned results by nationality of artist
-   **order** - *string* (optional) - order the results
    -   `rank` *default* - order by rank (starting at 1)
    -   `3y_slope` - order by those increasing their rank by the most over the past 3 years
    -   `surname` - order by artist's surname (A-Z)

### Results

-   **ArtistID** - The ID of the artist, use this when getting the Artist Details
-   **Link** - The link to the artist's page on ArtFacts.Net
-   **Graph** - The link to the artist's graph on ArtFacts.Net
-   **Name** - The first name of the artist
-   **Surname** - The surname of the artist
-   **Nationality** - The nationality of the artist
-   **BirthDates** - The birth (and death) dates of the artist
-   **Rank** - The artist's current ArtFacts.Net Rank
-   **3y_slope**  - The change of the artist's ArtFacts.Net Ranking over the past 3 years
-   **RankingDate** - When the ArtFacts.Net Ranking was generated for this artist
-   **MergedIDs** - Sometimes an artist has aliases or is otherwise entered twice into the ArtFacts.Net database. The MegredIDs property allows you to see which artist were duplicates of the current artist.

### Examples

Get the top 100 artists

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/top

Get the top 200 artists

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/top?limit=200

Get the artists ranked from 50-100

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/top?offset=50&limit=50

Get the top 100 artists ordered by surname

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/top?limit=50&order=surname

## Up and Coming


Gets the list of the "Up and Coming" artists based on the ArtFacts Ranking.

    GET /v0/ranking/upandcoming/

### Parameters

-   **limit** - *int* (optional) - number of artists to return
    -   min = 1
    -   max = 1000
-   **offset** - *int* (optional) - offset of the returned artists
    -   min = 1
-   **nationality** - *string* (optional) - filter returned results by nationality of artist
-   **years** - *int* (options) - set the number of years from which the "up and coming" status is calculated
-   **order** - *string* (optional) - order the results
    -   `rank` *default* - order by rank (starting at 1)
    -   `3y_slope` - order by those increasing their rank by the most over the past 3 years
    -   `surname` - order by artist's surname (A-Z)

### Results

-   **ArtistID** - The ID of the artist, use this when getting the Artist Details
-   **Link** - The link to the artist's page on ArtFacts.Net
-   **Graph** - The link to the artist's graph on ArtFacts.Net
-   **Name** - The first name of the artist
-   **Surname** - The surname of the artist
-   **Nationality** - The nationality of the artist
-   **BirthDates** - The birth (and death) dates of the artist
-   **Rank** - The artist's current ArtFacts.Net Rank
-   **3y_slope**  - The change of the artist's ArtFacts.Net Ranking over the past 3 years
-   **RankingDate** - When the ArtFacts.Net Ranking was generated for this artist
-   **MergedIDs** - Sometimes an artist has aliases or is otherwise entered twice into the ArtFacts.Net database. The MegredIDs property allows you to see which artist were duplicates of the current artist.

### Examples

Get the top 100 up and coming artists

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/upandcoming

Get the top 200 up and coming artists

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/upandcoming?limit=200

Get the 50-100 up and coming artists

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/upandcoming?offset=50&limit=50

Get the top 100 up and coming artists ordered by surname

    curl -u valid-user:password https://api.artfacts.net/v0/ranking/upandcoming?limit=50&order=surname

## Artist Search


Searches ArtFacts.net for a specific artist.

    GET /v0/artist/search/<search+criteria>/

### Parameters

There are no parameters for the Artist Search request, however, the search criteria should be embedded in the URL itself, suitably encoded of course.

See the examples below for more details.

### Results

If a search request finds any matching artists, it will return an array of objects, each object containing the following details:

-   **ArtistID** - The ID of the artist, use this when getting the Artist Details
-   **Link** - The link to the artist's page on ArtFacts.Net
-   **Graph** - The link to the artist's graph on ArtFacts.Net
-   **Name** - The first name of the artist
-   **Surname** - The surname of the artist
-   **Nationality** - The nationality of the artist
-   **BirthDates** - The birth (and death) dates of the artist
-   **Rank** - The artist's current ArtFacts.Net Rank
-   **3y_slope**  - The change of the artist's ArtFacts.Net Ranking over the past 3 years
-   **RankingDate** - When the ArtFacts.Net Ranking was generated for this artist
-   **MergedIDs** - Sometimes an artist has aliases or is otherwise entered twice into the ArtFacts.Net database. The MegredIDs property allows you to see which artist were duplicates of the current artist.

### Examples

Find Andy Warhol 

    curl -u valid-user:password https://api.artfacts.net/v0/artist/search/andy+warhol/

Finds all artists called Andy

    curl -u valid-user:password https://api.artfacts.net/v0/artist/search/andy/

This will also find Andy Warhol

    curl -u valid-user:password https://api.artfacts.net/v0/artist/search/warhol+andy/

## Artist Details


Gets the full details for a specific artist.

    GET /v0/artist/<ID>/


### Parameters

There are no parameters for this request, instead the ID of the artist required should be embedded in the URL itself.

See the example below for more details.

### Results

-   **ArtistID** - The ID of the artist, use this when getting the Artist Details
-   **Link** - The link to the artist's page on ArtFacts.Net
-   **Graph** - The link to the artist's graph on ArtFacts.Net
-   **Name** - The first name of the artist
-   **Surname** - The surname of the artist
-   **Nationality** - The nationality of the artist
-   **BirthDates** - The birth (and death) dates of the artist
-   **Rank** - The artist's current ArtFacts.Net Rank
-   **3y_slope**  - The change of the artist's ArtFacts.Net Ranking over the past 3 years
-   **RankingDate** - When the ArtFacts.Net Ranking was generated for this artist
-   **MergedIDs** - Sometimes an artist has aliases or is otherwise entered twice into the ArtFacts.Net database. The MegredIDs property allows you to see which artist were duplicates of the current artist.

### Examples

Get the details for Andy Warhol (ID = 328)

    curl -u valid-user:password https://api.artfacts.net/v0/artist/328/



----
* [index](README.md)
* [authentication](authentication.md)
* [end points](endpoints.md)
  
