# scraping light novel data
I scraped readlightnovel.me to get data on all of the light novels there using bs4 and requests

## What I did:
I used requests to access the novel list on the site, extracted all the novels by letter, and for each novel I extracted a bunch of parameters:
name, alternative name, artists, author, description, genres, original language, latest chapters, taring, status, tags, total views, type, year, similar novels, chapter count, and 100 most frequent words in a random chapter.


## Some things I did I am not so happy with:
1.  I assumed all chapter names are numbered, which was not true (some chapters were called epilogue for example). This might have messed up my chapter counts and random chapter content extraction
2.  I threaded the scraping, which is completely unneccessary looking back. I did this considering that this is an I/O bound task, but forgot to consider that doing so migh look like a website attack from the other end. 
3.  I formatted the genres into a single cell

## How I would fix them if I did this again:
1. I would count the existing chapters to get an accurate chapter count, create a list of links to each chapter, and access that list through the random number. This will allow me to not care about chapter names whatsoever. 
2. A simple for loop over the links, maybe followed by a time.sleep to not lose connection. 
3. Get a list of the genres (either hardcoded before scraping or through the scrape itself) and use each genre as a key


