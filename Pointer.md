
![img](https://media.geeksforgeeks.org/wp-content/uploads/20230223170531/2.png)

To explain the image above, "Address of pointer variable ptr" can be obtained by using "&ptr". "Value of variable var" can be obtained by using "\*ptr". "Address of variable var" can be obtained by using "ptr"


## \* 符號（解參考運算符）：

在指標的上下文中，* 被稱為解參考運算符。它用於解除指標所指向的值，即從記憶體位置中獲取存儲的實際數值。

當你有一個指向變數的指標時，使用 * 可以獲取該變數的值。

int x = 10;

int \*ptr = &x; // ptr 是一個指向 x 的指標

int value = \*ptr; // value 將變成 10，因為 \*ptr 解參考 ptr 所指向的值

  
  

## & 符號（取址運算符）：

在變數的上下文中，& 被稱為取址運算符。它用於獲取變數的記憶體地址，以便可以創建指向該變數的指標。

當你想要將變數的位址傳遞給函數或賦值給指標時，可以使用 &。

int x = 10;

int \*ptr = &x; // ptr 是一個指向 x 的指標，&x 取得 x 的記憶體地址

總之，* 用於解除指標並獲取其指向的值，而 & 用於取得變數的記憶體地址以創建指標。這兩個運算符是指標在 C 語言中操作中的核心工具。

## Example:

```
char* temp = "hi dumdum";

printf("%s\n", temp);    // Printing the string "hi dumdum"
printf("%d\n", temp);    // Printing the address of the string (memory address)
printf("%d\n", *temp);   // Printing the ASCII value of the first character ('h')
printf("%d\n", &temp);   // Printing the address of the pointer variable

char** doublePtr = &temp;

printf("Original String: %s\n", temp);          // Printing the string "hi dumdum"
printf("Address of String: %p\n", (void*)temp); // Printing the address of the string
printf("Value of Double Pointer: %p\n", (void*)doublePtr);  // Printing the address of the double pointer
printf("Dereferenced Double Pointer: %s\n", *doublePtr);    // Printing the string using double pointer
```
