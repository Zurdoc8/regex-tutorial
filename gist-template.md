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
There are 6 flags in javascript and when in use they could affect the search.

- i When in use, the search is case-insensitive meaning there is no difference between "A" and "a"
- g Known as the "global" flag meaning it will search for all and any matches, if it is not being used the search will stop after the first match.
- m Multiline mode
- s Enables "dotall" mode, that allows a dot "." to match newline character "\n"
- u Enables full Unicode support or the correct processing of surrogate pairs.
- y Enables "Sticky" mode to search at the exact position in the text.

Those are the 6 flags for regEx in javascript. Use them accordingly to enhance your search or match regEx.
### Grouping and Capturing
Grouping and capturing can be used to group regex components between parentheses _()_, curly brackets _{}_, square brackets _[]_, and/or backslashes \_ to different ends or effects on the regEx.
### Bracket Expressions
- [] regEx inside the [] indicate a set of characters to match. If "^" is used before the regEx within the brackets it will match anything BUT the characters inside the brackets.
- {} curly brackets are used to specify an exact amount of things to match and will always be preceded by a regEx _example [na]{2} would match "na" twice or [na]{2, 6} would match "na" between 2 and 6 times_
- () these represent remembered matches. When these matches are remembered they can later be used in find-and-replace operations or when you have to do something with part of the match. Using the expression component "$n" where "n" is any number from 0-9 a value can be assigned to each remembered match.  
### Greedy and Lazy Match
Probably the easiest way to describe these two terms would be:

- Greedy Match = match the longest possible string.
- Lazy Match = match the shortest possible string.
### Boundaries
Denoted by "\b" which acts like an anchor depending on where in the expression it is used:
    - Before the first character in a string if the first character is a word character.
    - After the last character in a string if the last character is a word character.
    - Between two characters in a string if one is a word character and the other is not. 


<img width="718" alt="image" src="https://user-images.githubusercontent.com/97048430/170188251-246fd108-4575-42a6-a4ed-aeb8be34ee3e.png">


### Back-references
Backreferences match the same text as previously matched by a capturing group. In order to know which number to use for a particular backreference simply look at the regEx from left to right anf cound the opening parentheses of each capturing group. First would be "1", Second parentheses would be "2" etc. The same one can be used multiple times within the same expression. The max amount of capturing groups supported by the engine is 99. 

Example: ([a-c])x\1x\1 matches _axaxa_, _bxbxb_, and _cxcxc_
### Look-ahead and Look-behind
In these instances a match would only be validated if it meets some additional criteria such as _followed by_ or _preceded by_ a specific character or set of characters.

Examples:
- Look-Ahead a(?=d) would only match an _a_ only if it is followed by _d_ and would not affect the rest of the regEx in any other way.
- Look-Behind (?<=d)a would only match an _a_ only if it is preceded by _d_ and would not affect the rest of the regEx in any other way.

If you use "!" as a negation operator in place of the "=" in the examples above it will do the exact opposite:

- Look-Ahead a(?!d) would only match an _a_ only if it is NOT followed by "d"
- Look-Behind (?<!d)a would only match an _a_ only if it is NOT preceded by _d_ and would not affect the rest of the regEx in any other way.
## Author

![Andres](https://user-images.githubusercontent.com/97048430/170190977-96bf83a1-b8bc-40e3-8f37-b8cd66f9bfb2.JPG)

- Zurdoc8 [Go to My GitHub](https://github.com/Zurdoc8)
- For questions you may reach me at [email](mailto:garelan@gmail.com)

## References
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes
- https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
- https://www.javascripttutorial.net/regular-expression-word-boundaries/
