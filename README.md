# SQLlite-Application
This mobile application is a basic SQLite-based user management system developed using Android Studio. It allows users to add, view, update, and delete records, making it suitable for educational purposes or as a foundation for more complex database applications.



User Interface Overview
The interface consists of multiple EditText fields and buttons for user interaction. The design is simple, with a soft green background and purple buttons to make it user-friendly and visually appealing. At the top, we have fields for entering a user’s name and password, followed by buttons labeled "add user" and "View Data." These elements provide basic functionalities for adding and viewing stored user data.

Functionality

Add User:
To add a user, the application collects input from the "Enter Name" and "Enter Password" fields. When the "add user" button is clicked, the addUser function in the MainActivity.java file is called. This function checks if the name and password fields are filled. If they are, the input data is passed to the MyDbAdapter class to insert it into the SQLite database. The MyDbAdapter class handles database operations such as inserting new records into the "myTable" table. Upon successful insertion, a toast message informs the user that the addition was successful. If unsuccessful, an error message is displayed.

View Data:
The "View Data" button allows users to retrieve all data stored in the database. When clicked, it calls the viewdata method, which in turn fetches all records using the getData method in MyDbAdapter. The method retrieves each row from the database and displays it in a toast message, helping the user view the data stored without needing to navigate away from the main screen.

Update User:
The update functionality allows users to modify an existing user's name. Two input fields are provided: "Current Name" and "New Name." When the "update" button is clicked, the update method is called. This method checks if both the old and new name fields are filled and then sends the data to MyDbAdapter to update the record in the database. The update is performed by matching the current name in the database and replacing it with the new name. A toast message is shown to indicate whether the update was successful.

Delete User:
To delete a record, the user enters the name of the person to be deleted in the "Enter Name to Delete Data" field and clicks the "delete" button. The delete method in MainActivity.java is called, which uses MyDbAdapter to remove the record from the database. If the deletion is successful, a confirmation message appears; otherwise, an error message is displayed.

Database Management
The MyDbAdapter class manages database interactions. It contains methods for inserting, updating, deleting, and retrieving data from an SQLite database. The database schema is defined in the myDbHelper nested class, which extends SQLiteOpenHelper. This class includes table creation and version upgrade logic. When the application runs for the first time, it creates a table named "myTable" with columns for a unique ID, user name, and password.

Error Handling and Messages
To improve user experience, the app provides toast messages for feedback. The Message class handles these messages, displaying feedback after each action so that users are informed of the success or failure of their operations.

Overall, this application demonstrates basic CRUD (Create, Read, Update, Delete) operations with SQLite in Android, making it a good foundation for anyone looking to understand database handling in mobile applications. This app can be further expanded by adding features like user authentication, data encryption, or a more sophisticated UI.
