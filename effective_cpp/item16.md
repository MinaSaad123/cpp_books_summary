# Item 16: Use the same form in corresponding uses of new and delete

There is wrong
```cpp
std::string *stringArray = new std::string[100];
delete stringArray;
```