Now we'll set up the "game plan", which is how the services interact with our app. In this case, we'll set up auth and Firestore:

1. In the FlutterFlow UI Builder, add an 'Onboarding Flow' widget to your screen. This will handle user registration and login.
2. Select the Firebase auth methods that you have enabled in Firebase console.
3. For Firestore, add a 'List' or 'Detail' widget to any screen where you want to fetch or display data from Firestore.
4. Configure the Firestore path, which is like the "address" of the data in your Firestore database.