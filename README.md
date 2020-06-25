# Machine Learning Capstone

### Where to open Bob’s awesome underground alternative music venue.


###### 1. Description of the problem

Bob Smith has recently come into a modest sum of money, and would like to fulfill his dream of opening a mid-sized music venue where he can book both local and larger performance artists, as well as providing a safe and interesting hangout for not only himself but people of all adult groups. While he has the money to invest, he still needs to be prudent in his use of the funds so he still has some limitations financially.  He also wishes to open specifically within the city of Fargo, North Dakota (For what reason only the gods may speculate).

**1. Overhead/Rent** - He needs to find a large enough space to host events and that would be suitable to house a small kitchen, a bar, a barista bar, and a seating section. He needs space while minimizing rent overhead.

**2. Crime** - He needs to be somewhere that economizes rent, but where violent crime is minimized, in order to cut down on venue security and provide a safer environment for his patrons.

**3. Accessibility** To Desired Demographic - Since it will be a music venue, his venue will likely need to be at least accessible to younger college-aged crowds who may not have reliable transportation. Being a music venue, having access to hotels might be desirable, and also being located in relative proximity to nearby places of congruous interests may also be valuable.

###### 2. Background, Data, and Approach

**Pricing:**

There are a total of 38 neighborhoods within the city of Fargo itself (defined from Zillow’s OpenDataSoft), and median property value (ZHVI) can be also pulled in csv format from their site at https://www.zillow.com/research/data/ . While home value does not equal commercial property, it can be used to make general assumptions regarding relative costs likely associated.

**Crime:** 
While there are crime stats available for consumption, I thought it might be interesting to use a keyword search from Google and to scrape sites indexed there in order to create a crime index. Using Python’s request module to fetch and to Beautiful Soup to parse content from open sites, I compare a selection of keywords associated with violent crime to count the number articles that reference both crime and the neighborhood in question. (This is actually my first attempt at a Crawler/Scraper function, despite coding for quite a few years now).

**Categories:**

The category index is derived from the FourSquare API’s category attribute, and a list of unique venue categories is generated. From that list, a weighted list is manually generated based on the types of venues that would be indicative of a good area to open shop. Iterating through the venues, an index is created based on the number of most relevant venues within a given neighborhood.