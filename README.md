# nosql-challenge
## General Overview
- The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Tasks
- Part 1: Database and Jupyter Notebook Set Up
    - Imported the data provided in the establishments.json file from the Terminal. Named the database uk_food and the collection establishments. Copyed the text used to import your data from the Terminal to a markdown cell in the notebook.
    - Within the notebook, imported the libraries you need: PyMongo and Pretty Print (pprint).
    - Created an instance of the Mongo Client.
    - Confirmed that the database was created and loaded the data properly:
        - Listed the databases you have in MongoDB. Confirmed that uk_food is listed.
        - Listed the collection(s) in the database to ensure that establishments is there.
        - Found and displayed one document in the establishments collection using find_one and displayed with pprint.
    - Assigned the establishments collection to a variable to prepare the collection for use.
- Part 2: Update the Database
    - Added new restaurant to database
    - Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.
    - Updated the new restaurant with the BusinessTypeID.
    - The magazine is not interested in any establishments in Dover, so checked how many documents contain the Dover Local Authority. Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
    - Some of the number values are stored as strings, when they should be stored as numbers.
        - Used update_many to convert latitude and longitude to decimal numbers.
        - Used update_many to convert RatingValue to integer numbers.
- Part 3: Exploratory Analysis
    - Answered specific questions they wanted, to help them find the locations they wish to visit and avoid.
        - Query #1: Which establishments have a hygiene score equal to 20?
        - Query #2: Which establishments in London have a RatingValue greater than or equal to 4?
        - Query #3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
        - Query #4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
