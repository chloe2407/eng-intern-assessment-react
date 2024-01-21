# **Overview**
This was done for Shopify's 2024 Front-End Engineering Internship Technical Challenge. For <a href="https://github.com/Shopify/eng-intern-assessment-react/pull/143">this pull request</a>, I implemented a stopwatch application using React and TypeScript, with start, stop, lap, and reset functionalities. The unit tests implemented ensure the correctness of such features.

# Changed Files
## App.tsx:
- Component representing the main application.
- Renders the `StopWatch` component, along with some styling for the overall stopwatch application.
## Stopwatch.tsx:
- Component that represents a stopwatch with time display and lap functionality.
- Uses React hooks, including` useState` and `useEffect`, to manage the state of various variables, including
    - **isPaused**: A boolean indicating whether the timer is running or paused. Initially set to `true`.
    - **currentTime**: An integer representing the current elapsed time in seconds. Initially set to `0`.
    - **currentLapCount**: An integer representing the current lap count. Initially set to `0`.
    - **lapTimes**: An array containing the lap times in seconds, initially an `empty array`.
- The `useEffect` hook is utilized to create and clear an interval timer when the component mounts or when the `isPaused` state changes. The timer increments the **currentTime** every second when the stopwatch is not paused.
- The component provides functions like `handleStartPause`, `handleReset`, and `handleLap` to control the stopwatch state when corresponding buttons are clicked.
- The `formatTime` function converts a given time in seconds to the format `hh:mm:ss`.
- The rendered JSX includes a time and lap display, button controls (via the StopWatchButton component), and a list of lap times. The most recent lap is displayed at the top of the list.
    - The lap times are formatted and displayed in a reverse order, showing the most recent lap at the top. The lap times are calculated as the difference between consecutive lap time entries.
    - The StopWatchButton component is imported and used to handle start/pause, reset, and lap actions.
## StopWatchButton.tsx:
- Component that represents buttons for controlling a stopwatch.
- The component takes props with the following interface:
    - **handleStartPause**: A function to handle the start/pause action.
    - **handleReset**: A function to handle the reset action.
    - **handleLap**: A function to handle the lap action.
    - **isPaused**: A boolean indicating whether the stopwatch is paused, which determines the state of the start/pause button.
 - The component returns a JSX structure that includes three buttons:
     - Start/Pause Button:
         - The button has dynamic styling based on the `isPaused` prop, using the `start-button` class when paused and the `pause-button` class when running. 
         - The button label alternates between "Start" and "Pause" based on the` isPaused` prop.
         - The onClick event is linked to the `handleStartPause` function, triggering the corresponding action.
    - Reset Button:
        - The button has a fixed styling with the `reset-button` class.
        - The onClick event is linked to the `handleReset` function, triggering the corresponding action.
    - Lap Button:
        - The button has a fixed styling with the lap-button class.
        - The onClick event is linked to the `handleLap` function, triggering the corresponding action.
- The component utilizes the aria-label attribute for accessibility, providing meaningful labels for screen readers.
- The buttons are wrapped in a container with the class custom-button-container.
- The styling of the buttons is handled by CSS classes (custom-button, start-button, pause-button, reset-button, lap-button). The styling includes custom colors, hover effects, and active effects.
- The component is designed to be reusable, accepting various callback functions to handle different actions associated with stopwatch controls.

# Added Files
## style.css:
- A styling sheet used throughout various files of the app. Includes responsive design.
## __tests__/StopWatch.test.tsx and __tests__/StopWatchButton.test.tsx:
-  Introduced tests using `@testing-library/react` and `Jest`.
- Tests cover critical functionalities: starting the timer, stopping the timer, recording laps, and resetting the timer.
- Used `jest.useFakeTimers()` for controlling time in tests.

# Purpose
The modifications have been implemented to provide a comprehensive and tested Stopwatch application. The introduced features improve user engagement, and the conducted tests verify the accuracy and reliability of the application's functionality

# Testing
All new features have been thoroughly tested with unit tests.
Manual testing has been conducted to ensure UI/UX consistency and functionality.

# Demo Video:

https://github.com/Shopify/eng-intern-assessment-react/assets/66324599/3e2e721f-77e1-41b2-aa84-5bd264b3dfc6

---
# Shopify's Technical Instructions
1. Fork this repo to your local Github account.
2. Create a new branch to complete all your work in.
3. Write tests to ensure you've completed the requirements
3. Create a Pull Request against the main branch when you're done and all tests are passing

# Project Overview
The goal of this project is to implement a stopwatch application using React and TypeScript. The stopwatch should have the following functionality:

- Start the stopwatch to begin counting time.
- Stop the stopwatch to pause the timer.
- Displays Laps when a button is pressed.
- Reset the stopwatch to zero.

You will be provided with a basic project structure that includes the necessary files and dependencies. Your task is to write the code to implement the stopwatch functionality and ensure that it works correctly.

## Project Setup
To get started with the project, follow these steps:

1. Clone the project repository to your local development environment.

2. Install the required dependencies by running npm install in the project directory.

3. Familiarize yourself with the project structure. The main files you will be working with are:
    - src/App.tsx: The main component that renders the stopwatch and handles its functionality.
    - src/Stopwatch.tsx: A separate component that represents the stopwatch display.
    - src/StopwatchButton.tsx: A separate component that represents the start, stop, and reset buttons.

4. Review the existing code in the above files to understand the initial structure and component hierarchy.

## Project Goals
Your specific goals for this project are as follows:

1. Implement the stopwatch functionality:
    - The stopwatch should start counting when the user clicks the start button.
    - The stopwatch should stop counting when the user clicks the stop button.
    - The stopwatch should reset to zero when the user clicks the reset button.
    - The stopwatch should record and display laps when user clicks the lap button.

2. Ensure code quality:
    - Write clean, well-structured, and maintainable code.
    - Follow best practices and adhere to the React and TypeScript coding conventions.
    - Pay attention to code readability, modularity, and performance.

3. Test your code:
    - Write unit tests for the stopwatch functionality to ensure it works correctly.
    - Verify that the stopwatch starts, stops, resets, and records laps as expected.

4. Code documentation:
    - Document your code by adding comments and explanatory notes where necessary.
    - Provide clear explanations of the implemented functionality and any important details.

5. Version control:
    - Use Git for version control. Commit your changes regularly and push them to a branch in your forked repository.

 6. Create a Pull Request:
    - Once you have completed the project goals, create a pull request to merge your changes into the main repository.
    - Provide a clear description of the changes made and any relevant information for the code review.

## Getting Started
To start working on the project, follow these steps:

1. Clone the repository to your local development environment.

2. Install the required dependencies by running npm install in the project directory.

3. Open the project in your preferred code editor.

4. Review the existing code in the src directory to understand the initial structure and component hierarchy.

5. Implement the stopwatch functionality by modifying the necessary components (App.tsx, Stopwatch.tsx, StopwatchButton.tsx).

6. Run the application using npm start and test the stopwatch functionality.

7. Commit your changes regularly and push them to a branch in your forked repository.

8. Once you have completed the project goals, create a pull request to merge your changes into the main repository.

## Resources
Here are some resources that may be helpful during your work on this project:

- [React Documentation](https://reactjs.org/docs/getting-started.html) - Official documentation for React, providing detailed information on React concepts and usage.

- [TypeScript Documentation](https://www.typescriptlang.org/docs/) - Official documentation for TypeScript, offering guidance on TypeScript features and usage.

- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) - Explore React Testing Library, a popular testing library for React applications.
