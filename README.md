# nosql-challenge
I am to evaluate food ratings data in order to help food critics decide where to focus their future articles.

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