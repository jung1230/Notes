
### Compile the code
```
g++ -std=c++17 NAME.cpp -o NAME
```

### Run the code
```
./NAME
```

### Use Valgrind to check for potential memory leaks
```
valgrind --leak-check=full <executable name> <command line arguments>
```

### quiz1
1. Always use delete\[ ] to deallocate memory for arrays allocated with new\[ ], and use delete to deallocate memory allocated with new (for single objects). This helps prevent memory leaks and other memory-related issues.
###### eg: 
```
void B(){
  int *ptr= new int;
  *ptr=5;
  delete ptr; 
}
```



