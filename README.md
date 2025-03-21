# Commit 1 Reflection notes

## Inside the `handle_connection` Method  

### 1. Receiving `TcpStream` as a Parameter  
The `handle_connection` method receives a `stream`, which is of type `TcpStream`. This type is used for reading and writing data over a TCP connection.  

### 2. Creating a `BufReader`  
Next, the `handle_connection` method creates a `BufReader` that wraps the `stream` to process data line by line.  

### 3. Reading the HTTP Request Line by Line  
- The `lines()` method is used to read the data stream one line at a time.  
- The `map()` function converts each line into a `String`.  
- This process continues until an empty line is found using `take_while()`.  
- Finally, `collect()` gathers the lines into a `Vec<String>` containing the HTTP request lines.  
- This data is stored in the `http_request` variable.  

### 4. Printing the HTTP Request  
Finally, the `handle_connection` method prints the contents of `http_request`.  
