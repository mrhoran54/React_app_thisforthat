

So my task for this project was to make a clone of  http://itsthisforthat.com.

First things first how to run this on your machine. Here are the few easy steps:

1. extract the files
2. run 'pip install -r requirments.txt' to get all the right versions of dependencies for this project
3. now run 'npm install react react-dom' and 'npm install body-parser' and 'npm install mongoose'
4. Finally make sure you have mongodb installed- I used this website: https://docs.mongodb.com/manual/tutorial/install-mongodb-enterprise-on-os-x/
5. First get mongo going: run 'sudo mongod' or just 'mongod'
6. Now time to get the server up and running our locally hosted api: cd into the api folder and then run 'npm run dev'
7. Now finally time to boot up the website: go into the my-app folder and enter 'npm start'
8. Now go to http://localhost:3000/ to check it out!

I'm breaking up my process into two parts:

1. website

So first of all I knew I wanted to use React because it was something I had been meaning to learn and builds on my exisisting javascript knowledge. That meant I had to go into the React docs and learn the basics from there. I then messed around with their tic tac toe game to get used to state and the various syntax nuances. On my first rendition of the app, I used the hard coded this and that arrays from the origical website to make sure my website was rendering the information and it all looked good with my new JCX/React knowledge. It looks good. Now time to deal with the API.

**One note: I changed the functionality slightly so that you can change just the 'this' or just the 'that' value: I thought it was more fun to make it customizable if you found a funny phrase and wanted to cycle through the other values to get the best pairing.

2. API

At first I just used their api http://itsthisforthat.com/api.php?json. From there I immediately was stumped by the fact that I couldn't just ingest all the this that pairings from the API at once and store that into the array. I thought a lot about all the different ways that I could just iterate over all the pairings, checking to see if I had added them into the array, and putting them all into an array. I wanted to make it as efficient as possible, eliminating extraneous api calls. But it didn't make sense. So I would just call the API on the onclick function to generate the new pairing. At first I had to deal with the whole concept of CORS (Cross-Origin Resource Sharing) with the no 'Access-Control-Allow-Origin header provided' error. One way to deal with that is using a proxy server, such as  https://cors-anywhere.herokuapp.com/ . This made my website render slowly. So the I decided to just write my own API. That way I could set my own headers and not worry about the proxy server. And there you have it!


Here are the articles and resrouces that I used:

https://medium.com/netscape/hacking-it-out-when-cors-wont-let-you-be-great-35f6206cc646
https://blog.hellojs.org/fetching-api-data-with-react-js-460fe8bbf8f2
https://github.com/facebook/create-react-app#creating-an-app
https://medium.com/@dinyangetoh/how-to-build-simple-restful-api-with-nodejs-expressjs-and-mongodb-99348012925d
