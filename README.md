# Vue.js Task Tracker App

This is a Task Tracker app built with Vue.js, Vite.js, and Vue Router. It allows you to track tasks with their associated day, time, and reminder status. The app provides CRUD (Create, Read, Update, Delete) functionality for managing tasks. The data is stored in a JSON file and can be accessed through a simulated backend using JSON Server.

## Prerequisites

Before running this application, make sure you have the following installed on your machine:

- Node.js (v14 or above)
- npm (v6 or above)

## Installation

1. Clone this repository to your local machine using the following command:
git clone https://github.com/MianHamzaHussain/vuewithvite

2. Navigate to the project directory:
cd vue-task-tracker

3. Install the dependencies:
npm install

## Development

To start the development server and launch the application, follow these steps:

1. Start the JSON Server by running the following command:
npm run backend

This will start the JSON Server and serve the `db.json` file as a RESTful API at `http://localhost:5000`.

2. Open a new terminal tab and run the following command to start the development server:
npm run dev

This will start the Vite development server and launch the application at `http://localhost:5173`.

3. Open your web browser and visit `http://localhost:5173` to see the Task Tracker app in action.

## Usage

- To add a new task, click on the "Add Task" button. Fill in the task details, including the task text, day, time, and reminder checkbox.

- To mark a task as a reminder, toggle the reminder checkbox next to the task.

- To edit a task, click on the task you want to edit and make the desired changes in the form that appears.

- To delete a task, click the delete button (usually represented by a trash can icon) next to the task.

## JSON Server

This application uses JSON Server to simulate a backend RESTful API. The data is stored in the `db.json` file. You can modify the data directly in this file, and the changes will be reflected in the application.

For more information on how to use JSON Server, refer to the [official documentation](https://github.com/typicode/json-server).

## Deployment

To build the production-ready version of the application, run the following command:
npm run build


This will generate the optimized and minified files in the `dist` directory. You can deploy these files to any static file hosting service or server of your choice.

## Credits

This Task Tracker app was created with the help of Vue.js, Vite.js, Vue Router, and various supporting libraries and tools. Special thanks to the open-source community for providing such powerful frameworks and utilities.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to modify and use it for your own purposes.
