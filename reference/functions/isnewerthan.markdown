---
layout: default
title: Function isnewerthan
categories: [Reference, Functions,Function isnewerthan]
published: true
alias: reference-functions-function-isnewerthan.html
tags: [reference, functions, function isnewerthan]
---

### Function isnewerthan

**Synopsis**: isnewerthan(arg1,arg2) returns type **class**

  
 *arg1* : Newer file name, *in the range* "?(/.\*)   
 *arg2* : Older file name, *in the range* "?(/.\*)   

True if arg1 is newer (modified later) than arg2 (mtime)

**Example**:  
   

```cf3
body common control

{
bundlesequence  => { "example" };
}

###########################################################

bundle agent example

{     
classes:

  "do_it" and => { isnewerthan("/tmp/later","/tmp/earlier"), "linux" }; 

reports:

  do_it::

    "The derived file needs updating";

}
```

**Notes**:  
   

This function compares the modification time of the file, referring to
changes of content only.