## Trie 
A Trie data structure in C++

#### Insert
Insert a string.

```c++
#include "trie/trie.h"

Trie *trie = new Trie();

trie->insert("a string");
```

#### Contains
Check if string exists in trie.

```c++
if(trie->contains("a string"))
    std::cout << "String found\n";
```

#### Prefix
Get vector of strings starting with a given prefix.

```c++
auto prefixed = trie->find("a str");

for(const auto &str: prefixed)
    std::cout << str << '\n';
```

#### Remove
Remove a string from trie.

```c++
trie->remove("a string");
```

#### String count
Number of strings in trie.

```c++
std::cout << "Strings in trie: " << trie->string_count << '\n';
```

#### Caching
Vector results of find are cached by default, you can disbale this by setting caching to false.

```c++
trie->caching = false;
```

The cache is cleared automatically if a string is removed from the trie, but if you insert after the initial build you will have to manually clear the cache.

```c++
trie->insert("new string");
trie->clear_cache();
```

#### Compiling

```
g++ main.cpp trie/trie.cpp -std=gnu++17 -Wall -Wextra -Werror -O3 -o search
```