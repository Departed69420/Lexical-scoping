# Example of lexical scoping in R

# Define a function that creates a closure
make_counter <- function() {
  count <- 0  # Variable count is local to make_counter function
  
  # Define a nested function that increments count
  increment <- function() {
    count <<- count + 1  # Use <<- to modify count in the enclosing environment
    return(count)
  }
  
  return(increment)  # Return the nested function
}

# Create an instance of counter using make_counter
counter <- make_counter()

# Test the counter
print(counter())  # Output: 1
print(counter())  # Output: 2
print(counter())  # Output: 3
