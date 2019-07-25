# Fridge
Food Expiration Date Tracker🍅🥚🍆<br>

![fridgepic](https://user-images.githubusercontent.com/18627505/61831484-d0665800-ae22-11e9-8900-f8b52f0554a5.png)

## About
Fridge is a food expiration date tracker.
It tells you when your food is going to expire.

## Timeline
May.27.2019 ~ Jun.13.2019

## How to use
I made this app for my school project within 3 weeks.
I often forget a food expiration date that I bought.
In order to remind me of the used-by date, I made Fridge app.

### Registering a food information
To save your food information, you can select food group. Then go to food lists of the food group.
After that, set the expiration date and quantity.

<img width="900" alt="Screen Shot 2019-07-24 at 10 05 23 PM" src="https://user-images.githubusercontent.com/18627505/61847343-2822b480-ae5f-11e9-87b0-df773516e258.png">

### Registered food list
As below image, you can see food name, expiration date and count until the expiration date.
<img width="350" alt="Screen Shot 2019-07-25 at 1 30 27 AM" src="https://user-images.githubusercontent.com/18627505/61859043-33d0a400-ae7c-11e9-89e8-525bdceeba76.png">

### Re-save and Delete
In detail page, edit information and click button!<br>
<img width="345" alt="Screen Shot 2019-07-25 at 1 29 21 AM" src="https://user-images.githubusercontent.com/18627505/61858868-cf154980-ae7b-11e9-8f1f-9998f7848dd3.png">

## Development

### Architecture
MVC is used in this app.
This is my directory.<br>
<img width="175" alt="Screen Shot 2019-07-25 at 1 39 28 AM" src="https://user-images.githubusercontent.com/18627505/61859529-2667e980-ae7d-11e9-9880-c48c21ad7d62.png">


### Database
To store data, It is used Cloud Firestore.
As Field, I prepared 4 field: "category", "foodName", "quantity", "usebyDate".<br>
This is my code to save data to Firestore.
```
private func sendDataToFireStore(categoryName: String, foodName: String, quantity: Int, usebyDate: Date) {

  var ref: DocumentReference? = nil
    let db = Firestore.firestore()
    ref = db.collection("usebyInfo").addDocument(data: [
        "category": categoryName,
        "foodName": foodName,
        "usebyDate": usebyDate,
        "quantity": quantity
    ]) { err in
        if let err = err {
            print("Error adding document: \(err)")
        } else {
            print("Document added with ID: \(ref!.documentID)")
        }
    }
}
```




