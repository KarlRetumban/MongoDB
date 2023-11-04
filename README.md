# Clothing Reviews Data as Document JSON Data
### Tool used is MongoDB

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

![alt text](https://github.com/KarlRetumban/Sample2/blob/main/images/mongoimport_code.PNG)

```cmd
mongoimport --db Reviews --collection rentedclothing_reviews --file renttherunway_final_data.jsonrenttherunway_final_data.json
```

#### Data collection view in MongoDB
![alt text](https://github.com/KarlRetumban/Sample2/blob/main/images/Data.PNG)


### NoSQL queries using the rented clothing review data
```mongodb

db.createCollection("reviews")


db.reviews.insertMany([
{trip:"Darwin City Stroll", reviewer:"Evan Drinkeld", rating:10, review:"The city stroll itself was filled with adventure", date: "2023-07-20"},
{trip:"Jabiru Park Walk", reviewer:"Patti Fanshaw", rating:9, review:"This walk was absolutely amazing! ", date: "2023-08-15"},
{trip:"East Arnhem Land Beach Walk", reviewer:"Kristoffer Tremathack", rating:9, review:"The beach walk and the coast was beautiful.", date: 
"2023-06-10"},
{trip:"Kings Canyon Uluru Walk", reviewer:"Kylila Landall", rating:7, review:"The views were breathtaking.", date: "2023-06-10"},
{trip:"Katherine Riverside Walk", reviewer:"Hilton Rolfini", rating:10, review:"The riverside walk is perfect.", date: "2023-02-17"},
{trip:"Darwin Hidden Valley Tourist Walk", reviewer:"Bridie Calbaithe", rating:8, review:" The views were breathtaking.", date: "2023-05-14"},
{trip:"Lake Woods Conservation Covenant Trail", reviewer:"Noah Pickthall", rating:9, review:"This walk was absolutely amazing.", "date": 
"2023-08-15"},
{trip:"Darwin City Stroll", reviewer:"Hilary Crawford", rating:2, review:"I did not like the walk, because it was so hot.", "date": "2023-06-10"},
{trip:"Darwin City Stroll", reviewer:"Marianna Gerhold", rating:7, review:"We explored city places, met friendly people", date: "2023-05-19"},
{trip:"Mataranka Park Trail", reviewer:"Kellby Rome", rating:6, review:"The trail is fun and I enjoyed it.!", date: "2023-01-16"},
{trip:"Darwin City Stroll", reviewer:"Zea Bernard", rating:3, review:"I did not enjoy the walk, it was tiring", date: "2023-04-18"},
{trip:"East Arnhem Land Beach Walk", reviewer:"Barbie Rappaport", rating:8, review:"Great and stunning ocean views!", date: "2023-02-15"},
{trip:"Darwin City Stroll", reviewer:"Marcelia Thorndale", rating:1, review:"I did not like the walk, I was tired", date: "2023-04-18"},
{trip:"East Arnhem Land Beach Walk", reviewer:"Vannie Lucks", rating:8, review:"Great views and I like the sea breeze! I highly recommend 
this walk on the beach to anyone visiting the area.", date: "2023-03-15"}])
```
