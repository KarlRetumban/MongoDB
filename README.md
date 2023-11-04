# Clothing Reviews Data (JSON Documents) in MongoDB
The tool used is MongoDB Compass.

We will import the rented clothing reviews JSON data and run NoSQL queries in mongoshell.

_____________________________

### Description of the data
The dataset contains information about rented attires for certain occassions. It also includes the ratings given by the renters. The user feedback or user review is also included in the data as well as information about the user and the attire.

### Import data to MongoDB Compass using 'mongoimport'
We use the command prompt in importing the rented clothing review data.
Below is the code used.

![alt text](https://github.com/KarlRetumban/Sample2/blob/main/images/mongoimport_code.PNG)

Here's what each part of the command does:

##### --db: Specifies the target database where you want to import your data.

##### --collection: Specifies the target collection within the database.

##### --file: Specifies the path to the JSON file you want to import.


In our case, the database named "Reviews" a collection named "rentedclothing_reviews" and your JSON file is named "renttherunway_final_data.json," you would run the code below:

```cmd
mongoimport --db Reviews --collection rentedclothing_reviews --file renttherunway_final_data.jsonrenttherunway_final_data.json
```

#### Data collection view in MongoDB Compass
Below is the view of the rented clothing review document collections in MongoDB Compass. There are a total of 192,544 documents in the 'rentedclothing_reviews' collection. The fields included are:


* fit
* user_id
* bust size
* item_id
* weight
* rating
* rented for
* review_text
* body type
* review_summary
* category
* height
* size
* age
* review_date

![alt text](https://github.com/KarlRetumban/Sample2/blob/main/images/Data.PNG)


_____________________________________________


### Run NoSQL Queries
We run the following NoSQL queries using the rented clothing review data.

##### 1. Get the highest reviews given. We also convert the rating to integer first since it is in string format.
   
```mongodb
db.rentedclothing_reviews.aggregate([
  {
    $project: {
      rating: { $toInt: "$rating" }
    }
  },
  {
    $sort: { rating: -1 }
  },
  {
    $limit: 1
  }
])
```

##### 2. Get average rating by dress category
   
```mongodb
db.rentedclothing_reviews.aggregate([
  {
    $project: {
      category: 1,
      rating: { $toInt: "$rating" }
    }
  },
  {
    $group: {
      _id: "$category",
      averageRating: { $avg: "$rating" }
    }
  }
])
```

##### 3. Total number of rents per dress category
   
```mongodb
db.rentedclothing_reviews.aggregate([
  {
    $group: {
      _id: "$category",
      count: { $sum: 1 }
    }
  }
])
```

##### 4. Get the average age of renters by dress category
   
```mongodb
db.rentedclothing_reviews.aggregate([
  {
    $project: {
      category: 1,
      age: { $toInt: "$age" }
    }
  },
  {
    $group: {
      _id: "$category",
      averageAge: { $avg: "$age" }
    }
  }
])
```
