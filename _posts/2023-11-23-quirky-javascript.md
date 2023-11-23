---
author: Theo Okafor
description: JavaScript is a versatile and dynamic programming language. However, as you delve deeper into its intricacies, you will often encounter some peculiarities that make you wonder. In this article, we will explore some of these aspects of JavaScript that you probably did not know about.
image: https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg
---

# Quirky JavaScript: Strange but True JavaScript Anomalies

## Introduction

JavaScript, the language that powers the interactive side of the web, is a versatile and dynamic programming language. However, as you delve deeper into its intricacies, you will often encounter some peculiarities that make you wonder.  In this article, we will explore some of these aspects of JavaScript that you probably did not know about.

## 1. 0.1 + 0.2 is NOT Equal to 0.3

If you try the following codes on your browser console you may be shocked to find that 0.1 + 0.2 === 0.3 returns false.

```jsx
0.1 + 0.1 === 0.2 // true
0.1 + 0.2 === 0.3 // false
0.1 + 0.3 === 0.4 // true
```

The simple reason why this happens is because JavaScript floating point maths is off in a particular instance. **`0.1 + 0.2 = 0.30000000000000004 // which is not exactly equal to 0.3`.** Computers generally are not very good at dealing with floating point numbers. This explains why, in JavaScript’s defence, this problem is also found in Python, Ruby, etc.

## 2. “Plus-able” Arrays and  Objects

The plus operator (+) in JavaScript does Mathematical addition and concatenation, just like in most programming languages. Concatenation is where JavaScript simply joins things together

For Example:

```jsx
'Dot' + 'Campus' // 'DotCampus'
23 + ' years'    // '23 years'
null + ''        // 'null'
undefined + ''   // 'undefined'
[] + ''          // ''
```

From the examples above JavaScript is clearly converting everything to string before it concatenates them. This is proven further by the following examples:

```jsx
[] + [] // ""
['Dot'] + ['Campus']  // 'DotCampus'
```

If you are coming from a Python Background you would have expected an empty `list` and a `list` containing ‘Dot’ and ‘Campus’ i.e. `[’Dot’, ‘Campus’]`. Nope, not in JavaScript, and that is not all. 

```jsx
'1' + 2 // '12'
1 + '2' // '12'
{} + [] // 0 
[] + {} // '[object Object]'
```

I know what you’re thinking. “What is going on here?” 😂 If you know the explanation for any of these, please leave a comment for us to learn.

## 3. Here comes “typeof”

JavaScript's `typeof` operator is very handy for identifying variable types. It does it reliably well and gives expected results in most cases. For example:

```jsx
typeof 'word'    // 'string'
typeof 2         // 'number'
typeof {}        // 'object'
typeof true      // 'boolean'
typeof undefined // 'undefined'
```

In other cases, it gives unexpected results, like these:

```jsx
typeof []    // 'object' NOT 'array'
typeof null  // 'object' NOT 'null'
typeof NaN   // 'number' NOT 'NaN'
```

## 4. == vs. ===

JavaScript offers both loose equality (`==`) and strict equality (`===`) operators. While the latter checks both value and type, the former opts for more lenient comparisons. For example:

```jsx
'2' == 2  // true
'2' === 2 // false
```

Understanding these nuances is crucial to avoiding pitfalls.

## 5. Automatic Semicolon Insertion

JavaScript is forgiving when it comes to semicolons. It employs Automatic Semicolon Insertion (ASI) to add semicolons where it thinks they should be. While this feature is designed for convenience, it can lead to unexpected results. For example, consider:

```jsx
return
{
    value: 42
};

```

Surprisingly, the object literal is not treated as expected. Due to ASI, the interpreter inserts a semicolon after `return`, turning the code equivalent to `return;` with the subsequent block treated as unreachable.

As ridiculous as they may seem, most of these JavaScript nuances have reasonable explanations behind them, and as we have seen some of them are not really peculiar to JavaScript only. The goal is to know them, understand them and use them advantageously.
