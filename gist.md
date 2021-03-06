# Regex tutorial

Have you ever wondered what the string of numbers and symbols used in a search pattern is? Well, look no further. These expressions, called regex expressions were developed by computer scientist Stephen Cole Kleene and describe how you might search for something in vast amounts of text. 

/[ap+]\l(e|s)/

What word am I searching for? Today I will be explaining how regex searches for different characters and numbers in a text editting software. In the expression above, the search is telling it to look for a series of alpha numeric characters in the following paragraph: 

Apples are the best. They have the flavor of a sweet and tart candy. When you bite into an apple the tast is great. Even aligators like apples! 

In searching for ap+ it is looking for something that returns a word with ap and more than one 'p' characters after it. Therefore, this search would most likely return the word apple, but we will see more as we continue to explore what the characters mean. 

## Summary

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Today, we will be exploring the expression above. Theroughout this tutorial we will try to understand what the different components of the search for this email help us do when trying to match a person or email with the one above. Ultimately, the symbols as well as groupings give us a sense of where to go. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

In a regex expression, we can break the components into anchors, quantifiers, grouping constructs, bracket expressions, character classes, or operators, flags and character escapes. Each of these symbols or group of symbols plays a role in understanding how the search is created. By understanding these roles, you can interpret this foreign seeming expression above. 

### Anchors

Anchors are the pieces of the regex experession that tell us what our expression may start and end with. 

If you ever see a ^ this symbolizes the beginning or starting word. In this case the starting string is represented by this portion of text: 

^([a-z0-9_\.-]+)

The carrot tells us to look for the beginning string that has letters a-z and numbers 0-9. We will explore a little more in depth the other components of this string in a minute. 

The ending string is signified by a $. As we see in the following code 

([a-z\.]{2,6})$

Ultimately, this is telling the user to look for a string at the end that contains letters between a and z. We will again explore this further in future sections. 

### Quantifiers

The quanitifiers tell you how many of a specific character might follow. Quantifiers can be shown by a * ? or {}. In the expression we are exploring today, the quantifiers are expressed with curly braces. Let's take a look at our ending sequence from above. 

([a-z\.]{2,6})$

As we explained, the sequence is looking for letters between a and z and then a period. However, what do the 2 and 6 mean? In this example, the syntax of {2,6} tells us that it can have between 2 and 6 of those characters in our ending string. 

For example, in a more simplified version, I might have a{2,6}. This means that the string with have between 2 and 6 'a' characters at the end of the string. Because in our email example, we have a more complicated search criteria, it means that we can have between 2 and 6 alphabet characters at the end. 

### Grouping Constructs

In regex expresions, parenthesis serve to group the characters and search patter into parts. For example, in our starting string of code, 

^([a-z0-9_\.-]+),

the () tell the computer to search for the first string in the way outlined inside the parenthesis. In this example, it is looking for a string of numbers and letters. Because we have grouped using a parenthesis, anything that comes within a string on its own with be searched.

### Bracket Expressions

In bracket expressions, the information will search for anything that has those characters. If we take a look at our ending expression,

[a-z\.]

the brackets surround the range from a to z. This means that the search will return anything that has a lower case a, b, c, ..., z. As a final note, the alphabet is lower case, meaning that it will only find lowercase strings of letters. 

As another example, as we said above, [a-z0-9_\.-] will search for anything with a lower case letter from a-z and number form 0 to 9. 

### Character Classes

Anything with a \ may be determined to be aa character class. In this example I see it in both the ended and begining strings as \.. In both of these cases. the \. is telling it to search for anything that does not have a new line. The character classes in general tell the search what type of thing to look for. For example \W means to look for whitespace and \d means to look for a digit. 

@([\da-z\.-]+)\.

In looking at this phrase, the \. is telling the search to look for soemthing with lower case letters or numbers between 0 and 9 which do not have the new line character. Because of the @, the characters need to come after the @ in the email and not create a new line at that point. 


### The OR Operator

The OR operator can be shown in two different ways with [] or (|). In the case above we only have brackets. However, I will also show you how you could change these to parentheses notation. Let's take a look at our ending sequence again. 

[a-z\.]

The brackets tell this search to look for a letter between a and z. This means the letter could be a or b or c or d or ... Additionally, you see the characters \ and . after the letters. Because of bracket notation, it reads the string must have the letters or the period. 

If I were to convert this to parenthesis notation, it might look like 

(a|b|c|d|e|f|g|h|i|j|k|l|m|n|o|p|q|r|s|t|u|v|w|x|y|z)

as the | serves the place that or might in english. 

### Flags

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Usually regex expressions need to be wrapped in // in order to tell the computer to search for what is within the slashes. The one exception is in the case of flags. In the expression above, there are no flags. However, if instead we had /i at the end of the expression, this would tell the search to conduct it as if it was case insensitive. 

### Character Escapes

Finally, the last type of character which is important to point out is the \. as you have seen before the \ might mean that you should search for a specific class. However, it might also mean that you need to search for a specific character. For example, 

[a-z0-9_\.-]

in this string of characters, the \ tells the computer that it might have a period or a -. 


## Author

I am teacher turned bootcamp professional, working to understand the complexities behind javascript. I have developed a toolkit in order to help me understand and read code in a variety of contexts and look forward to entering the ever changing field of coding!

<a href= "https://github.com/hlodg">Hannah's Github</a>
