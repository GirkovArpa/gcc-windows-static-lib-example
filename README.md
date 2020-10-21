- main.cpp
```cpp
#include <iostream>
extern void foo();
int main() { 
  std::cout << "main()" << std::endl; 
  foo();
} 
```
- foo.cpp
```cpp
#include <iostream>
void foo() { 
  std::cout << "bar" << std::endl; 
}
```
Console commands:
```sh
$ g++ -o foo.obj -c foo.cpp
```
```sh
$ ar rcs foo.lib foo.obj
```
```sh
$ g++ main.cpp foo.lib -o main.exe
```
These spells conjure up the static lib **foo** with the executable **main** statically linked to it.
