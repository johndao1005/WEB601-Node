# WEB601-Node

testing node methods

1. `process.pid`: This process's ID
   target the process by using its ID
2.  `process.argv`: A list of command-line argument supplied to this process  
    `argv` property, which is an array which contain all the command-line invocation
    arguments.  
    Using Javascript to loop through all the command-line

    ```Javascript
    const http = require('http')
    const port = 3000
    debugger
    http.createServer((req, res) => {
    res.writeHead(200, {'Content-Type': 'text/plain'})
    debugger  
    res.end('Hello World\n')
    }).listen(3000, () => {
    console.log(`Server running at http://localhost:${port}`)
    })
    ```

3. `process.env`: A list of environment variables
   Access the environment variable either in env file or current environment  
   This can retrieve the environment variable. For example:  
    Using the current environment

    ```Javascript
    USER_ID=239482 USER_KEY=foobar node app.js
    ```

    ```Javascript
    process.env.USER_ID // "239482"
    process.env.USER_KEY // "foobar"
    ```

    Access the variables in env file
    
    ```Javascript
    require('dotenv').config();

    process.env.USER_ID // "239482"
    process.env.USER_KEY // "foobar"
    process.env.NODE_ENV // "development"
    ```

4. `process.platform`: Platform name, such as `darwin` for macOS
   
5. `process.release`: This Node's release URL
   
6. `process.versions`: A list of versions of Google Chrome V8, zlib, uv, etc.
   
7. `process.stdin()`: The standard input (for reading)
   
8. `process.stdout()`: The Standard output (for writing)
   
9.  `process.uptime()`: Time of how long this process is running
    
10. `process.memoryUsage()`: Resident set size, total heap and used heap memory usage
    
11. `process.exit()`: Terminating this process
    `SIGKILL` is the signal to immediately terminate the process which similar with `process.exit()`
    while `SIGTERM` would gracefully terminate the process. The signal would send to process managers
    ```Javascript
    process.on('SIGKILL', () => {
    server.close(() => {
    console.log('Process terminated')
        })
    })
    ```
12. `process.kill()`: Termination of another process
    similar with `process.exit()`, `process.kill()` handle the termination but the target would be another process  
    `process.kill(process.pid, 'SIGTERM')`
    `SIGTERM` can be change as `SIGKILL` like `process.exit()`