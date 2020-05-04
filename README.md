# Movies-ETL2
Fatal issues with first repo, creating 2nd

##Synopsis of Module 8 Challenge assignment

##The code in Challenge.py will EXTRACT json and/or csv files, transform the data into orderly and complimentary formats, and LOAD the resulting data into Postgres.

## Because the aim of this project was to automate a process that can ideally be run hands-off it is important to list the assumptions in place.

## These are
    ##We use urls beloging to websites to extract data.  These urls could change unexpectedly, in which case our automated ETL pipeline would be broken.  A good pipeline has a minimum of hardcoded inputs, but in this case urls are a required hardcode.

    Loading of the data into Postgres requires a user password.  If there are prorocols that require regularly updated password resets that will require an update to dependent cofiguration files.

    Analysis in the development of this process concluded that there were like headers in separate data sources that could and should be taken going forward as being identical.  Columns such as Adaptation by and Writer were assumed to be identical in meaning.

    The data sources had some, but very few, adult films listed.  We elected to remove the category completely and permanently.  There is probably another a better source of data for adult films than the one we are creating here.  Please note that a message will generate should any adult film not be removed during parsing.

    Additionally. we are using 3 very different data sources.  To ensure the Wiki data is scribbed with Kaggle Metadata an error message will generate if the Extract does not occur.  Existing tables for both the MetaData/Wiki merge and the ratings will be replaced with each interation.

    The ratings data resource was extensive, with over 26,000,000 ratings available.  Our assumption is that the volume of ratings data is neither problematic norresource demanding, and is in fact likely to only increase over time.

    Lastly, in the course of building this ETL process certain bad or corrupted data was removed from inclusion.  Efforts were made to ensure the code was dynamic enough to include the vast majority of data.  However, a small number of movies were removed from the database due to bad data.  In the future it is possible that the source data will be revised or corrected, but this ETL will likely still not capture the updated movies.