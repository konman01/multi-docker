# MultiDocker Application

The pupose of application to develope the react application running using multiple containers. React application to used to provide interface to submit 
value to calculate the fibonnaci value of an index. Postgress database container is used to store the index for which the fibo is calculated. Reddis is 
used to store the recent indices.

<img width="1436" alt="react-app" src="https://user-images.githubusercontent.com/33331778/197665066-5877017b-50ac-46dc-8797-82797b62ff52.png">

## Developement set up

React server container contains the react app running on port 3000 to host the web application. All request submitted by the user through the React app, will be forworded to Express server container to perform the operations to to calculate the fibonacci of a number.Postgress database container is used to store the index for which the fibo is calculated. Reddis is used to store the recent indices. Worker container performs the heavy wait operation to calculate fibo of a number. When the index value is inserted into the redis database by the express application, operation will trigger at the worker container ro calculate the fibo of a number. Nginx conatiner is used to map request to  React application container and Express container.  

<img width="1099" alt="Screen Shot 2022-10-24 at 9 09 32 PM" src="https://user-images.githubusercontent.com/33331778/197665566-9d1786ec-dcbb-47a9-94c4-b990b1808081.png">

### Deployment Set up

Architecture of the production level applcation is as shown below. Applcation is hosted and tested in AWS. As we see in the diagram, we have used AWS RDS applcation to host the Progres database and Elastic cache to host the redis database. Production level docker compose file is created to set up the application in the Amazon Elastic BeanStalk. 

<img width="1154" alt="Screen Shot 2022-10-24 at 9 11 58 PM" src="https://user-images.githubusercontent.com/33331778/197665822-418e9a6d-765b-4eea-9c66-b13d4ea2e93f.png">

When ever we make changes to the applcaition and pushed into the master brach on git hub, Travis CI pull the code and executes all the test cases, if sucessfulk, it will deploy the application in AWS EBS. Below is the screenshot containing all the build performed for the application







