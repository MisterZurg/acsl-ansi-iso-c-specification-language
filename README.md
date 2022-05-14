# ACSL: ANSI/ISO C Specification Language for Visual Studio Code

A Visual Studio Code extension provides language support for the ANSI/ISO C Specification Langage (ACSL).

## Features

This extension provides basic features:
* C / C++ syntax highliting;
* including IntelliSense; 
* code navigation;
* code editing support.

```cpp
#include <stddef.h>
// Expressions inside /*@ ... */ will be highlited
/*@
    requires \valid(a+(0..n-1));
    
    assigns  a[0..n-1];
    
    ensures

    \forall integer i;
        0 <= i < n ==> a[i] == 0;
*/
// C++ syntax highliting
void set_to_0(int* a, size_t n){
    size_t i;
    // Also /*@ ... */ will be highlited
    /*@
        loop invariant 0 <= i <= n;
        loop invariant
    \forall integer j;
        0 <= j < i ==> a[j] == 0;
    loop assigns i, a[0..n-1];
    loop variant n-i;
    */
    // And again C++ syntax highliting
    for(i = 0; i < n; ++i)
        a[i] = 0;
}
```

⚠️ Note: the default syntax highlighting for ACSL files is provided by  TextMate rules writen from scratch.

# Contributing
I welcome your contributions and thank you for working to improve the ACSL development experience in VS Code. If you would like to help work on the VS Code ACSL  extension, please create a pull request.