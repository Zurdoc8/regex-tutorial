# regEx Tutorial 

regEx or Regular Expressions might seem scary at first sight but once you look at them closely they are not that complex. They can be extremely useful in different sutiuations. Most regEx have already been written so it is not like you will be re-inventing the wheel, you just have to look up the specific one for each situation. 

## Summary

A good example of a good use for regEx is when we are trying to match or validate an Email. Validating an Email is essential when you are creating a secure application through authentication. 

> Matching an email - /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

That string of code up there that looks like giberish at plain sight it can be used to validate if an e-mail is formatted correctly. Let's break it down to its components to try to make some sense of it and hopefully a little less scary.

- The first component we see is the symbol "^" or caret which must always go at the beggining of your regEx.
- Parentheses "()" are used to group a section of components together to increase specificity when validating.
- Our criteria will be captured in between Square Brackets "[]" to indicate the values we will be searching for within the email we are trying to validate.
- The first value we see is "a-z" which will look for at least one iteration of any lower-case letter in the Email. If we wanted to validate for capital letters the value would be "A-Z"
- The next value we are evaluating for is any number between "0-9" notice how we did not leave a space in between our two first values. 
- The backslash " \ " in a regular expression precedes a literal character in this case "." and "-" that may appear in our first section of our Email. It can alse be used in a different way but we will discuss that in another section further down.
- The Plus "+" sign denotes that any one of these values will be present at least once.

- The "@" or at symbol must be present in order for an Email to be validated. 

- "\d" matches a single character that is a digit.
- Our a-z again it is checking for at least one iteration of a lower-case letter.
- The previously reviewed component "\ .- " to look for literal characters.
- Again at the end of this section we have the Plus sign "+".

- The " \ ." is stating that a period or "dot" must be placed after the previous section. 

- The last section starts with our already well known "( [ a-z \ . ] )" combo.
- The next component to define is "{2,6}" which states that a character may occur between 2 and 6 times
- The last component we see is the "$" or dollar sign which must always be included at the end of your regEx.

Not so scary anymore, is it? This is just one of many regEx examples out there. Scroll down or use the table of contents to jump to the desired section where we will talk about a little more in depth of the different characters you may use in a regEx and their function.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors are symbols used to denote the beggining and the end of a regEx. In the example we saw above the beggining Anchor is "^" while the end anchor is "$". Anchors MUST always be present in a regEx.
### Quantifiers
Quantifiers will determine how many instances of a character, group or character class must be present. If these symbols "*, +, ?, and {}" are found in a regEx pattern they will be interpreted as quantifiers unless they are "escaped" as literal characters by using a " \ " in front of them. An escaped quantifier will be considered as a possible match and will not act as a quantifier anymore.

- "*" Asterisk - Match zero or more times.
- "+" Plus Sign - Match one or more times.
- "?" Question Mark - Match zero or one time.
- {n} Match exactly n times.
- {n,} Match at least n times.
- {n, m} Match from n to m times.
### OR Operator
The OR Operator is used when there are 2 or more options to choose from, so as long as they are separated by the "|" or pipe character. 

Example: ^ I like (dogs|cats), but not (wolves|lions).$

The expression above will match any of the following strings:

- I Like dogs, but not wolves.
- I like dogs, but not lions.
- I like cats, but not wolves.
- I like cats, but not lions.
### Character Classes
A character class defines a set of characters that help distinguish between letters and digits.

- "." The period or dot matches any single character except line terminators, however, inside a character class it just matches a literal dot.
- \d Matches any digit [0-9]
- \D Matches any character that is NOT a digit [^0-9]
- \w Matches any alphanumeric character from the alphabet (including the underscore "_"); [A-Za-z0-9 _]
- \W Matches any character that is NOT an alphanumeric character [A-Za-z0-9_]
- \s Matches a single white space character including _space, tab, form feed, line code and other Unicode spaces_ [ ]
- \S Matches a single character other than a white space. [^ ]
- \ Indicates that the character following the backspace should be treated specially (like the examples seen above), or that it needs to be "escaped" 

Just like the examples above there are other character classes that you can use to create regEx.
### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes