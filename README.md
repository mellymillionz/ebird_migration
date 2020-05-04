# ebird_migration
Exploratory analysis of ebird data 

##Data##:

On the Cornell Ornithology Lab’s ebird.org site you can request access to their data and explain why you want it. It’s takes some time to be granted access, but once you have it a century of bird data opens up to you. For this project, I filtered my dataset by New York City on the ebird site, and a few hours later I was emailed an enormous .txt file with my data!

Overview of NYC bird data:
To provide some context on the data, every row on ebird is an individual bird observation. A single bird watcher records where, when and what they saw with a rather detailed text description to accompany the 47 meta features. Incredibly, much of this data has been extremely well recorded over the past century, with only ten of the columns containing a majority missing values.

Additionally, the data comes in a package that also contains a kind of Readme guide in the form of a pdf which provides a thorough overview of the file format and each feature of the dataset.

**Important Feature Information:**

- Global Unique Identifier: Each bird sighting has a unique key.
- Common Name: The bird species. There are a total of 442 distinct species in this data.
- Category: A taxonomy detailing hybrids and non-natives, etc.
- Latitude/Longitude: Will be useful for mapping the bird sightings.
- Observation Date: The date the bird(s) were sighted, which I converted to a Datetime object.
- Observation Count: The number of birds of that species spotted on that particular sighting. Unfortunately, if this was not filled in by the birdwatcher it has been filled with an ‘X’.
- Locality Type: State (S), County (C ), Postal/Zip Code (PC), Town (T), Hotspot (H), Personal (P). Mainly I think the interested part here is the ‘hotspot’ to see if there really tend to be more sightings in those areas.
- Month: A column I created from Observation Date to be able to better track monthly movements.
- Year: A column I created from Observation Date to be able to better track monthly movements.
- Observer ID: To track specific birders.
- Number of Observers: Perhaps an intersting way to track habits of birders.
- Duration Minutes: How long did the bird actually spend there being observed?
- Trip Comments/Species Comments: A string of text about the experience written by the person who logged it.

##Interesting Questions for this Dataset:

After an initial exploration of the features, there are a number of things this data can tell us that I’m planning to explore going forward.

**Explore change in bird migration populations over time**: However, right off, there’s a a couple big issues. As smart phones and internet have become more common, everyday people have been reporting more bird sightings. This means that in the years since 2005, overall sightings have skyrocketed. Scaling the data then will be a big issue when looking at changes over time — I don’t think the white-throated sparrow population has increased 10x from the early 1900s!

**When is the best month to see specific birds?** Obviously many people have spent time thinking about and visualizing this particular aspect of bird migrations already, but it would be a great way to make some interesting subplot visualizations comparing when each bird species arrives, peaks, and leaves NYC.
Mapping bird sighting locations: Mapping bird sightings based on the latitude and longitude provides a great chance to do some visualizations over time. Might be a good time to brush up on those Plotly skills and using a slider to make the visualizations more interactive.

**Meta-information about the birders themselves!** One thing I love about this dataset is that there is actually a number of ways to find out information about the birders — do they travel in groups or solo? How long do they spend on each sighting? Are there any super sighters (aka people who log a lot of bird sightings). Finally, my personal favorite, the comments! This seems like a great opportunity to do a little natural language processing to see what birders are really paying attention to.

