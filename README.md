 SETUP AND DEPLOY (GOOGLE CLOUD/FIREBASE)
1 - Generate the application and download the code

2 - Configure Firebase

2.1 - Create a Firebase project at the Firebase Console.

2.2 - Enable Firestore Database

Go to Database
Click at 'Enable'
2.3 - Enable Storage

Go to Storage
Click at 'Enable'
2.4 - Enable Email/Password sign-in:

At the Firebase console, open the Auth section.
On the Sign in method tab, enable the Email/password sign-in method and click Save.
2.5 - Add the Firebase project id to the '<project-folder>/.firebaserc'.

2.6 - Configure the client side account's credentials:

Go to the Firebase Project.
Open 'Project settings'.
At 'Your apps', click at the web icon.
Copy only the content of the var 'config'.
Paste the content at the variable 'firebaseConfig' of the files:
'<project-folder>/frontend/src/config/localhost.js'
'<project-folder>/frontend/src/config/development.js'
'<project-folder>/frontend/src/config/production.js'
2.7 - Configure the server side account credentials:

Go to the Firebase Project.
Click at the configuration icon, placed near 'Overview' at the left corner.
Click at 'Project settings'.
Open the tab 'Service accounts'.
Open 'Firebase Admin SDK'.
Click at 'GENERATE NEW PRIVATE KEY'.
Save and replicate the file as:
<project-folder>/backend/service-accounts/localhost.json
<project-folder>/backend/service-accounts/test.json
<project-folder>/backend/service-accounts/development.json
<project-folder>/backend/service-accounts/production.json
3 - Configure email sender (Optional): In order to be able to send user invitation emails you need the SMTP credentials configured. It's optional, if you don't have it configured the app just won't send those emails.

Open '<project-folder>/backend/config/<environment>.json'.
Locate the 'email' section.
Configure the SMTP credentials. See https://nodemailer.com for config options.
4 - Configure Internationalization (I18n)

You must setup the labels for the entities, fields and roles.

4.1 - For each locale at 'frontend/src/i18n/<locale>.js':
Go to the 'entities' section.
Add the labels for the entity and it's fields.
Go to the 'roles' section.
Replace the object name for the label.
5 - Setup project dependencies

5.1 - Download and install NodeJS

Go to https://nodejs.org/en/blog/release/v8.11.4/, download and install 8.11.4v of NodeJS.

5.2 - Open the console at the project folder.

5.3 - Update NPM:

npm install -g npm

5.3 - Install firebase-tools globally:

npm install -g firebase-tools

5.4 - Login at firebase-cli and add the project:

firebase login

5.5 - Open the 'frontend' folder and run:

npm install

npm run deploy:development

5.6 - Open the 'backend' folder and run:

npm install

npm run deploy:development

6 - Open the application at the URL informed after first deploy

 RUN LOCALLY (GOOGLE CLOUD/FIREBASE)
1 - Setup and deploy first

You must first setup and deploy because you need the storage rules deployed at the Firebase.

2 - Open the 'backend' folder and run:

npm run start

3 - Open the 'frontend' folder and run:

npm run start