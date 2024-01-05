# nosql-challenge
I am to evaluate food ratings data for a magazine in order to help food critics decide where to focus their future articles.

I'll be using NoSQL, MongoDB, and PyMongo to query and analyze the data.

In part 1 of the project I will create a database. In part 2 I will update the database, and in part 3 i'll analyze the data.


# Summary

Part 1: Database and Jupyter Notebook Set Up

    - Use NoSQL_setup_starter.ipynb for this section of the challenge.


    - Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.

![Alt text](<Screen Shot 2024-01-04 at 7.54.15 PM.png>)

    - Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).

    - Create an instance of the Mongo Client.

    - Confirm that you created the database and loaded the data properly:

        - List the databases you have in MongoDB. Confirm that uk_food is listed.

        - List the collection(s) in the database to ensure that establishments is there.

        - Find and display one document in the establishments collection using find_one and display with pprint.

![Alt text](<Screen Shot 2024-01-04 at 7.55.34 PM.png>)

    - Assign the establishments collection to a variable to prepare the collection for use.

2. Update the Database

    - Use NoSQL_setup_starter.ipynb for this section of the challenge.

    - The food critics have requested some modifications for the database. Make the following changes to the establishments collection:

    - An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis. Add the following information to the database:

![Alt text](<Screen Shot 2024-01-04 at 8.00.07 PM.png>)

    - Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

![Alt text](<Screen Shot 2024-01-04 at 8.03.29 PM.png>)

    - Update the new restaurant with the BusinessTypeID you found.

    - The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.

![Alt text](<Screen Shot 2024-01-04 at 8.10.46 PM.png>)

    - Some of the number values are stored as strings, when they should be stored as numbers.

        - Use update_many to convert latitude and longitude to decimal numbers.

        - Use update_many to convert RatingValue to integer numbers.

![Alt text](<Screen Shot 2024-01-04 at 8.14.51 PM.png>)

3. Exploratory Analysis

    - The magazine has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.

    - Use NoSQL_analysis_starter.ipynb for this section of the challenge.

    - Some notes to be aware of while you are exploring the dataset:

        - RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.

            - Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.

        - The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.

    - Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.

        - Unless otherwise stated, for each question:

            - Use count_documents to display the number of documents contained in the result.

            - Display the first document in the results using pprint.

            - Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.

        - Which establishments have a hygiene score equal to 20?

![Alt text](<Screen Shot 2024-01-04 at 8.37.18 PM.png>)

        - Which establishments in London have a RatingValue greater than or equal to 4?

            - Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.

![Alt text](<Screen Shot 2024-01-04 at 8.39.08 PM.png>)

        - What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

            - Hint: You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.

![Alt text](<Screen Shot 2024-01-04 at 8.39.45 PM.png>)

        - How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

![Alt text](<Screen Shot 2024-01-04 at 8.40.08 PM.png>)