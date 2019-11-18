---
layout: post
title:  "Carriage Return vs Line Feed vs Form Feed! - First Post Ever :)"
date:   2019-11-18 03:15:00 +02
categories: misc
author: "Shendy"
---
This will be my first post ever published on the big internet :). I choose to share simple info in it to ease publishing this blog.  

<br />

I will show some examples that demonstrates the difference between **Carriage Return**, **Line Feed**, and **Form Feed**. I will use **Python** for the examples, but you can apply the info using any programming language.

<br/>

### Here is the main header in this article:
- [Line Feed `\n`](#line-feed-n-newline-end-of-line-eol-or-line-break)
- [Form Feed `\f`](#form-feed-f)
- [Carriage Return `\r`](#carriage-return-r)

<br />

### Line Feed `\n` (newline, end of line (EOL), or line break)
Normally when you print something using `print()` function, it will be printed with implicitly `\n` at the end which will force next text to start in next line.
So when you run multliple print after each other, you will see them like this:
```python
print('firstname: Ahmed')
print('lastname: Shendy')
```
```
firstname: Ahmed
lastname: Shendy
```

<br />

You can explicitly use `\n` in your print statement to ask start new line where it is placed.
```python
print('firstname: Ahmed\nlastname: Shendy')
```
```
firstname: Ahmed
lastname: Shendy
```

<br />

### Form Feed `\f`
It is used for giving some indentation. It will start new line and put some indentation that equals the number of letters of previous letters, then after that any followed text can begin. 
```python
print('*\f*\f*\f*')
```
```
*
 *
  *
   *
```

<br />

### Carriage Return `\r`
It is interesing one. It will not start new line at all, it will rather start in the beginning of the same line, and start typing next text from there, which means overriting previous printed text. Let's see by example.
```python
print('Original text')
print('Original text\rOverridden by this')
```
```
Original text
Overridden by this
```

Got it? another example?
```python
print('Ahmed Shendy')
print('Ahmed Shendy\rAyman')
```
```
Ahmed Shendy
Ayman Shendy
```

Don't get bothered by typing the original text in separate line, I am just using it for help.