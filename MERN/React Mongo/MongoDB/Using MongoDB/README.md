
#### :white_check_mark:  Each document you insert into this collection should have the following format: ({name: STRING, home_state: STRING, lucky_number: NUMBER, birthday: {month: NUMBER, day: NUMBER, year: NUMBER}})

## Output Format
#### Assignment Instruction
> Terminal Command
>> Result

## Output
#### :white_check_mark:  Create a database called 'my_first_db'
>\> use my_first_db
>> switched to db my_first_db

#### :white_check_mark:  Create students collection
>\> db.createCollection('students')
>>{"ok": 1}
#### :white_check_mark:  Create 5 students with the appropriate info
>\> db.students.insert({name: 'Alpha', home_state: 'California (San Jose Dojo)', lucky_number: 1, birthday: {month: 01, day: 01, year: 2001}})
>> WriteResult({"nInserted": 1})
####
>\> db.students.insert({name: 'Bravo', home_state: 'Washington (Seattle Dojo)', lucky_number: 2, birthday: {month: 02, day: 02, year: 2002}})
>> WriteResult({"nInserted": 1})
####
>\> db.students.insert({name: 'Charlie', home_state: 'California (San Jose Dojo)', lucky_number: 3, birthday: {month: 03, day: 03, year: 2003}})
>> WriteResult({"nInserted": 1})
####
>\> db.students.insert({name: 'Delta', home_state: 'Washington (Seattle Dojo)', lucky_number: 4, birthday: {month: 04, day: 04, year: 2004}})
>> WriteResult({"nInserted": 1})
####
>\> db.students.insert({name: 'Echo', home_state: 'California (San Jose Dojo)', lucky_number: 5, birthday: {month: 05, day: 05, year: 2005}})
>> WriteResult({"nInserted": 1})
#### :white_check_mark:  Get all students
>\> db.students.find({})
>> {"_id": ObjectId("6008c78e8ac9128a2f30c99c"), "name": "Alpha", "home_state": "California (San Jose Dojo)", "lucky_number": 1, "birthday": {"month": 1, "day": 1, "year": 2001}}<br/>
>> {"_id": ObjectId("6008c7968ac9128a2f30c99d"), "name": "Bravo", "home_state": "Washington (Seattle Dojo)", "lucky_number": 2, "birthday": {"month": 2, "day": 2, "year": 2002}}<br/>
>> {"_id": ObjectId("6008c79d8ac9128a2f30c99e"), "name": "Charlie", "home_state": "California (San Jose Dojo)", "lucky_number": 3, "birthday": {"month": 3, "day": 3, "year": 2003}}<br/>
>> {"_id": ObjectId("6008c7a38ac9128a2f30c99f"), "name": "Delta", "home_state": "Washington (Seattle Dojo)", "lucky_number": 4, "birthday": {"month": 4, "day": 4, "year": 2004}}<br/>
>> {"_id": ObjectId("6008c7a88ac9128a2f30c9a0"), "name": "Echo", "home_state": "California (San Jose Dojo)", "lucky_number": 5, "birthday": {"month": 5, "day": 5, "year": 2005}}
#### :white_check_mark:  Retrieve all students who are from: California (San Jose Dojo) or Washington (Seattle Dojo)
>\> db.students.find({home_state: 'Washington (Seattle Dojo)'})
>> {"_id": ObjectId("6008c7968ac9128a2f30c99d"), "name": "Bravo", "home_state": "Washington (Seattle Dojo)", "lucky_number": 2, "birthday": {"month": 2, "day": 2, "year": 2002}}<br/>
>> {"_id": ObjectId("6008c7a38ac9128a2f30c99f"), "name": "Delta", "home_state": "Washington (Seattle Dojo)", "lucky_number": 4, "birthday": {"month": 4, "day": 4, "year": 2004}}<br/>
####
>\> db.students.find({home_state: 'California (San Jose Dojo)'})
>> {"_id": ObjectId("6008c78e8ac9128a2f30c99c"), "name": "Alpha", "home_state": "California (San Jose Dojo)", "lucky_number": 1, "birthday": {"month": 1, "day": 1, "year": 2001}}<br/>
>> {"_id": ObjectId("6008c79d8ac9128a2f30c99e"), "name": "Charlie", "home_state": "California (San Jose Dojo)", "lucky_number": 3, "birthday": {"month": 3, "day": 3, "year": 2003}}<br/>
>> {"_id": ObjectId("6008c7a88ac9128a2f30c9a0"), "name": "Echo", "home_state": "California (San Jose Dojo)", "lucky_number": 5, "birthday": {"month": 5, "day": 5, "year": 2005}}
#### :white_check_mark:  Get all students whose lucky number is greater than 3
>\> db.students.find({lucky_number: {$gt: 3}})
>> {"_id": ObjectId("6008c7a38ac9128a2f30c99f"), "name": "Delta", "home_state": "Washington (Seattle Dojo)", "lucky_number": 4, "birthday": {"month": 4, "day": 4, "year": 2004}}<br/>
>> {"_id": ObjectId("6008c7a88ac9128a2f30c9a0"), "name": "Echo", "home_state": "California (San Jose Dojo)", "lucky_number": 5, "birthday": {"month": 5, "day": 5, "year": 2005}}
#### :white_check_mark:  Get all students whose lucky number is less than or equal to 10
>\> db.students.find({lucky_number: {$lte: 10}})
>> {"_id": ObjectId("6008c78e8ac9128a2f30c99c"), "name": "Alpha", "home_state": "California (San Jose Dojo)", "lucky_number": 1, "birthday": {"month": 1, "day": 1, "year": 2001}}<br/>
>> {"_id": ObjectId("6008c7968ac9128a2f30c99d"), "name": "Bravo", "home_state": "Washington (Seattle Dojo)", "lucky_number": 2, "birthday": {"month": 2, "day": 2, "year": 2002}}<br/>
>> {"_id": ObjectId("6008c79d8ac9128a2f30c99e"), "name": "Charlie", "home_state": "California (San Jose Dojo)", "lucky_number": 3, "birthday": {"month": 3, "day": 3, "year": 2003}}<br/>
>> {"_id": ObjectId("6008c7a38ac9128a2f30c99f"), "name": "Delta", "home_state": "Washington (Seattle Dojo)", "lucky_number": 4, "birthday": {"month": 4, "day": 4, "year": 2004}}<br/>
>> {"_id": ObjectId("6008c7a88ac9128a2f30c9a0"), "name": "Echo", "home_state": "California (San Jose Dojo)", "lucky_number": 5, "birthday": {"month": 5, "day": 5, "year": 2005}}
#### :white_check_mark:  Get all students whose lucky number is between 1 and 9 (inclusive)
>\> db.students.find({lucky_number: {$gte: 1, $lte: 9}})
>> {"_id": ObjectId("6008c78e8ac9128a2f30c99c"), "name": "Alpha", "home_state": "California (San Jose Dojo)", "lucky_number": 1, "birthday": {"month": 1, "day": 1, "year": 2001}}<br/>
>> {"_id": ObjectId("6008c7968ac9128a2f30c99d"), "name": "Bravo", "home_state": "Washington (Seattle Dojo)", "lucky_number": 2, "birthday": {"month": 2, "day": 2, "year": 2002}}<br/>
>> {"_id": ObjectId("6008c79d8ac9128a2f30c99e"), "name": "Charlie", "home_state": "California (San Jose Dojo)", "lucky_number": 3, "birthday": {"month": 3, "day": 3, "year": 2003}}<br/>
>> {"_id": ObjectId("6008c7a38ac9128a2f30c99f"), "name": "Delta", "home_state": "Washington (Seattle Dojo)", "lucky_number": 4, "birthday": {"month": 4, "day": 4, "year": 2004}}<br/>
>> {"_id": ObjectId("6008c7a88ac9128a2f30c9a0"), "name": "Echo", "home_state": "California (San Jose Dojo)", "lucky_number": 5, "birthday": {"month": 5, "day": 5, "year": 2005}}
#### :white_check_mark:  Add a field to each student collection called 'interests' that is an ARRAY. It should contain the following entries: 'coding', 'brunch', 'MongoDB'. Do this in ONE operation
>\> db.students.updateMany({}, {$addToSet:  {interests:  {$each:  ['coding', 'brunch', 'MongoDB']}}})
>> {"acknowledged": true, "matchedCount": 5, "modifiedCount": 5}
#### :white_check_mark:  Add some unique interests for each particular student into each of their interest arrays
>\> db.students.update({name:  'Alpha'}, {$addToSet:  {interests:  'Writing nicely structured .md files'}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
####
>\> db.students.update({name:  'Bravo'}, {$addToSet:  {interests:  'Obsessing over minor details'}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
####
>\> db.students.update({name:  'Charlie'}, {$addToSet:  {interests:  'Exceeding expectations'}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
####
>\> db.students.update({name:  'Delta'}, {$addToSet:  {interests:  'Stirring jelly with a spork'}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
####
>\> db.students.update({name:  'Echo'}, {$addToSet:  {interests:  'Watching Rick and Morty'}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
#### :white_check_mark:  Add the interest 'taxes' into someone's interest array
>\> db.students.update({name:  'Delta'}, {$addToSet:  {interests:  'taxes'}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
#### :white_check_mark:  Remove the 'taxes' interest you just added
>\> db.students.update({name: 'Delta'}, {$pop:  {interests: 1}})
>> WriteResult({"nMatched": 1, "nUpserted": 0, "nModified": 1})
#### :white_check_mark:  Remove all students who are from California
>\> db.students.remove({home_state:  'California (San Jose Dojo)'})
>> WriteResult({"nRemoved": 3})
#### :white_check_mark:  Remove a student by name
>\> db.students.remove({name: 'Bravo'})
>> WriteResult({"nRemoved": 1})
#### :white_check_mark:  Remove a student whose lucky number is greater than 5 (JUST ONE) 
##### Note from ninja:  Only one student remains.  Lucky number is 4.  Changing $gt: 5 to $gt: 3, then recreating students for following instructions.
>\> db.students.remove({lucky_number:  {$gt: 3}})
>> WriteResult({"nRemoved": 1})
#### :white_check_mark:  Add a field to each student collection called 'number_of_belts' and set it to 0
>\> db.students.updateMany({}, {$set:  {number_of_belts:  0}})
>> {"acknowledged": true, "matchedCount": 5, "modifiedCount": 5}
#### :white_check_mark:  Increment this field by 1 for all students in Washington (Seattle Dojo)
>\> db.students.updateMany({home_state:  'Washington (Seattle Dojo)'}, {$inc:  {number_of_belts:  1}})
>> {"acknowledged": true, "matchedCount": 2, "modifiedCount": 2}
#### :white_check_mark:  Rename the 'number_of_belts' field to 'belts_earned'
>\> db.students.updateMany({}, {$rename:  {number_of_belts: 'belts_earned'}})
>> {"acknowledged": true, "matchedCount": 5, "modifiedCount": 5}
#### :white_check_mark:  Remove the 'lucky_number' field
>\> db.students.updateMany({}, {$unset: {lucky_number: []}})
>> {"acknowledged": true, "matchedCount": 5, "modifiedCount": 5}
#### :white_check_mark:  Add a 'updated_on' field, and set the value as the current date
>\> db.students.updateMany({}, {$currentDate:  {updated_on:  true}})
>> {"acknowledged": true, "matchedCount": 5, "modifiedCount": 5}