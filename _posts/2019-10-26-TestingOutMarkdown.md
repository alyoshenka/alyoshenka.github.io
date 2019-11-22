---
title: Testing out Markdown
peek: various md formatting
---
This is my first post since reinvigorating my site.
This should show up in excerpt.

This should not show up in excerpt.


***

*italic*
_italic_

---

**bold**
__bold__

___

  
***italicbold***
___italicbold___
__*italicbold*__
**_italicbold_**

***

~~strikethrough~~

***

> This is a blockquote

> This is another blockquote
>> This is a nested blockquote

1. this
1. is
1. an
1. ordered
    1. indented
1. list

- this
* is
+ an
- unordered
- list

Here is an image

![image title here](/assets/images/skel.jpg)

`here is some code`

```cpp
    int main()
    {
        std::cout << "fenced code" << std::endl;
        return 0;
    }
```

This text should have a footnote[^boop]
# this line needs to be here
[^boop]: Here is the footnote

- [ ] unchecked
- [x] checked
- [ ] unchecked

Link to [github](https://github.com/alyoshenka "My github")

Tables

| col 1         | col 2         | col 3         |
| ------------- |:-------------:| -------------:|
|               |               | right-aligned |
|               | centered      |               |
| left-aligned  |               |               |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*more* | `columns` | **here**


