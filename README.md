# Task1

serealizers.py:-
In this file we just created a new class that extends the ModelSerializer of DRF. model in class Meta just specifies the model to use, while
fields can be a tuple or list holding the individual fields in the model, or takes in __all__ to just serialize all fields.


app.js :-
in line 1 and line 2 , we imported React and axios respectively.
In line 6 we set our initial state, which is just the respective fields in our post model. We use this to pass the FormData to the backend.
line 12 is where we handle form value changes to set our state to the value of the new input value. This method of using states in our forms in React is called Controlled Forms.
line 18 is an important one. We also set the state, but now the image property of our state is set to the the first file data of the event target, since the target is an array 
of files.
Another important part is the handleSubmit method in line 24. First, the default character of forms — which is reloading the web page — is prevented. Then a new instance of the 
in-built JavaScript’s FormData is instantiated by calling new FormData()in line 27 . One method of the FormData is append which takes in two required parameters — a key:value 
pair — with the first parameter being the key while the second is the value. The key should correspond to the field in your django models — this is important to avoid errors! 
The append method is called on the FormData passing in three different times to add the form values, now saved in the state. The FormData is now one large parcel of data that
is now passed as the body of our axios POST call to our Django REST API.

post/views.py :-
The parser_class is used because we are dealing with request data that comes in as FormData. Two class methods get and post are defined to handle the respective requests.
