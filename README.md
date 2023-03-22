# Project Overview

The Full Stacked workout app is a full stack application built by a team of three, with Ulas Temel (https://github.com/ulas312) and Ebrar Hassan (https://github.com/EbsH3). The application allows users to search through a collection of exercises and create a workout log by selecting exercises. The frontend of the application was built using React, while the backend and database were built using Node.js and MongoDB, respectively. The Material UI library was used for styling the application.

Deployment link: https://wyndhams-project-3-frontend.netlify.app/ 

# Brief

Our brief was as follows:
Create a full-stack app using MongoDB, Express, React and Node.js.
The app must have an authentication function.
It must include at least two models on the backend and multiple components on the frontend.

# Getting Started

Clone both backend and frontend repos locally using the SSH Key contained within the Code button above, then follow the steps below in a local Terminal window:

Open repos in your code editor of choice:
```
code .
```
Install the node modules:
```
npm install
```
For the backend, run:
```
npm run dev
```
For the frontend, run:
```
Npm start
```

Technologies Used

- React.js
- MongoDB
- Mongoose
- Express
- Node.js
- MUI
- SASS
- Git
- GitHub
- Excalidraw
- Slack
- Trello
- Zoom

# Planning

During the planning phase, the team defined the scope and features of the application, created a project timeline, and divided the development tasks among team members. The team also researched and selected the technologies and tools to be used in the project, as well as creating wireframes and mockups to guide the development process.

# Build Process

The build process for the Full Stacked workout app involved several stages, including planning, design, development, and testing. During the development phase, the team divided the tasks among members based on their areas of expertise and interest. My role in the project was to develop the API in the backend, as well as to create the routing and use React hooks in the frontend to display the required information from the database.

## Backend API Development
As the backend API developer, I was responsible for designing and implementing a RESTful API that allowed the frontend to communicate with the backend and to retrieve data from the database. This involved defining the API endpoints, creating the database schema and models, and implementing the logic for handling HTTP requests and responses.

```js
const getAllWorkouts = async (_req, res, next) => {
  try {
    const workouts = await Workouts.find();
    return res.status(200).json(workouts);
  } catch (e) {
    next(e);
  }
};

async function searchWorkouts(req, res, next) {
  console.log(req.query);
  try {
    const { search } = req.query;
    const workouts = await Workouts.find({
      $or: [
        { name: { $regex: search, $options: 'i' } },
        { description: { $regex: search, $options: 'i' } },
        { type: { $regex: search, $options: 'i' } },
      ],
    });
    return res.status(200).json(workouts);
  } catch (e) {
    next(e);
  }
}
```

I also had to ensure that the API was secure and scalable, by implementing authentication and authorization mechanisms, as well as optimising the database queries and indexing for fast and efficient data retrieval. 

…CODE…

## Frontend Development
In the frontend, I was responsible for creating the routing and using React hooks to display the required information from the database. This involved creating the necessary React components and designing the UI and layout of the application.

…CODE…

I also had to ensure that the frontend was responsive and user-friendly, by implementing features such as form validation, error handling, and feedback messages. To achieve this, I used a combination of React hooks, Material UI components, and other React libraries and tools.

…CODE…

Integration and Testing
Once the frontend and backend components were developed, the team had to integrate them and test the application as a whole. This involved testing the API endpoints and database queries, as well as testing the UI and user interactions. I should note that I had created endpoints within Postman to test this ahead of time prior to hooking up the backend and frontend.

I also had to collaborate with other team members to resolve any integration issues or bugs, as well as to provide feedback and suggestions for improvement.

Overall, my role in the build process of the Full Stacked workout app was critical to its success, as I created the API and frontend components that allowed the app to function smoothly and efficiently.

# Challenges

One of the main challenges of the project was integrating the frontend and backend components of the application. This involved designing and implementing a RESTful API to allow the frontend to communicate with the backend and to pass data between the two components. Another challenge was optimising the database schema and queries to ensure efficient and scalable data retrieval and storage.

# Key Learnings

One of the highlights of the project was the team's collaborative and agile development process, which involved regular communication over Slack and Zoom and planning via a morning stand-up, as well as utilising Git and GitHub for version control and code sharing. Another highlight was implementing accessibility features such as screen reader support for any images that were displayed across the app.

Working in a team of three, I had the opportunity to collaborate with other developers and to learn from each other's strengths and expertise. The team worked closely together throughout the project, communicating regularly and sharing updates on progress and issues. I also enjoyed working collaboratively to resolve differences in opinion, by listening to each other's perspectives and finding a compromise that worked for everyone. This helped to create a positive and supportive team dynamic, which in turn facilitated a more efficient and effective development process.

This positive attitude and willingness to take on challenges helped to create a dynamic and productive team environment, where everyone felt supported and encouraged to do their best work

# Future Development

Some possible directions for future development of the Full Stacked workout app include:
- Adding user profiles: User profiles could be added to allow users to save their workout history and preferences, as well as to view and follow other users.
- Adding workout plans: Pre-defined workout plans could be added to the app, allowing users to select and follow a pre-made plan based on their fitness level and goals.
- Adding social features: Social features such as a community forum or chat could be added to the app, allowing users to connect and share tips and advice.
- Adding more exercises: The app's exercise database could be expanded to include a wider variety of exercises and to allow users to create and submit their own exercises.
- Adding analytics: Analytics and data visualization features could be added to the app to help users track their progress and to provide insights into their workout history and trends.
