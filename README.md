# js-event-loops

### 1. What is the Event loop ?
 
 
 A loop that works during the runtime and is responsible for executing the code, collecting and processing events, and executing queued sub-tasks. 


### 2. Explain the 6 phases of the event loop

When Node.js starts, it initializes the event loop, processes the provided input script which may make async API calls, schedules timers, then begins processing the event loop. In the previous example, the initial input script consisted of console.log() statements and a setTimeout() function which schedules a timer. 

When using Node.js, a special library module called libuv is used to perform async operations. This library is also used, together with the back logic of Node, to manage a special thread pool called the libuv thread pool. This thread pool is composed of four threads used to delegate operations that are too heavy for the event loop. I/O operations, Opening and closing connections, setTimeouts are examples of such operations. 

When the thread pool completes a task, a callback function is called which handles the error(if any) or does some other operation. This callback function is sent to the event queue. When the call stack is empty, the event goes through the event queue and sends the callback to the call stack. 

* Timers:  This phase processes timers that have been set using setTimeout() and setInterval().
* Pending Callbacks: This phase processes any callbacks that have been added to the message queue by asynchronous functions.
* Idle: The “idle” phase is a period of time during which the event loop has nothing to do and can be used to perform background tasks, such as running garbage collection or checking for low-priority events.
* Poll: This phase is used to check for new I/O events and process any that have been detected.
* Check This phase processes any setImmediate() callbacks that have been added to the message queue.
* Close Callbacks: This phase processes any callbacks that have been added to the message queue by the close event of a socket

### 3. List some best practices in server-side code development

### 4. What is NPM5: How do you initialize a package in npm

### 5. How do you run a script in the package.json ?

To run scripts in the scripts property of a `package.json`, you'll need to use the default `npm run` command

### Initialize a package of your choice, give it a name and install the following npm packages to it, express, mongoose, joi.
