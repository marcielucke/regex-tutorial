# Regex explained: Matching an Email

When searching through code there may be times a user wants to specify a certain combinations of characters for the engine to search for. While we can perform this in generalized functions and loops, it may be more convenient to use Regex logic to gather the information needed. Regex is a tool that uses a organization of characters to find certain patterns within a string. It can also be used to validate certain inputs. In this tutorial, we will explore how to use a Regex feature to search for an email.



## Summary

The Regex below will find any emails within your specified code.

  `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

While this looks like gibberish at first, we will soon discuss how these characters indicate an email address. Regex can use both literal and meta characters to communicate what they want to grab from code. A literal character is exactly what it sounds like. For example, if you specify to find an A it will grab any uppercase A from the string. A meta character is more abstract, and will point towards a more abstract pattern. We will discuss these concepts further below. 

As a generalized rule, your regex code should be encapsulated between two forward slash characters. 


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

### Regex Components

Regex will use a variety of formulas to indicate what it is looking for.

[] anything inside the brackets represents a range. For example [abc] tells the regex to find strings that include a, b, or c. [a-z] will tell the code to look for any letter between a-z that is lowercased.

{} anything inside the curly bracelets represents limits for the regex match, such as maximum or minimum length.

() anything inside parenthesis will look for an exact match according to the order the characters are shown. It can also break up our regex formula into subexpressions by grouping sections together. 

\ a backslash will escape a character that would otherwise be taken literally. For example [\.] tells the code to match a period, rather than a universal quantifier, which we will discuss below. 


### Anchors

The code will often begin and end with an anchor. In our example, the anchors used are ^ and $.

The ^ signifies that the string we are looking for begins with whatever follows.

The $ signfies that the string we are looking for ends with the characters that precede it. 

### Quantifiers

Quantifiers will set the limits of the string for your desired regex match.
    i.e. maximum and minimum number of characters wanted for your search

There are generalized ways to indicate this, but also ways to make the search more specific. 

Generalized
    1. The asterisk (*) tells the regex to gather the preceding character zero or more times.
    2. The addition sign (+) tells the regex to gather the preceding character one or more times.
    2. The question mark (?) tells the regex to gather the preceding character zero or one time.

    `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

We see the + sign used in our first and second segments of code. It follows our brackets, and this indicates that we need at least one or more characters to be present to match the search.

Specific 
    Using the {} can tell our code to find a more specific quantity. Below are three ways this is used.
    1. {n} : matches exactly n times
    2. {n,} : matches at least n times
    3. {n,x} : matches a minimum of n and a maximum of x times

 `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

We see the {2,6} used in our last segment of code. This is telling the code to look for a series of letters between 2 and 6 characters long. 


### OR Operator

While the OR operator is not used in our code, it works similar to the OR function in JavaScript. 

Placing a | inbetween two characters within brackets tells the regex formula that either/or characters are a match. 

### Character Classes

Character Classes are used to define a set of characters. Examples are located below.

    * . matches any character aside from \n
    * \d matches any digit 
    * \w matches any alphanumerical character
    * \s matches a single whitespace

Capitalizing the letter will find the inverse of the desired method. 

    We see this used used multiple times in our regex formula. 

     `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The first instance where this is used is the \d in our second segment. This tells the regex to look for any digit in the string. 

Notice that the \. is not considered a class in the first segment of code. This is because the backslash indicates that we are looking for a literal period instead of any character. 

### Grouping

As mentioned earlier, we can break up our regex into subexpressions using parenthesis. We see this done three times in our code. First we will break down our desired action into 3 parts

    1. Email Name
    `([a-z0-9_\.-]+)` 

    2. Domain
    `([\da-z\.-]+)`

    3. Extension
    `([a-z\.]{2,6})`

Between these groups we see the literal characters @ and \. (a regular period), these tell the regex to look for exactly those characters between our other specified instructions. 


### Bracket Expressions

The brackets once again represent a range of characters to look for. Let's explore what these mean within our code.


    1. Email Name
    `([a-z0-9_\.-]+)` 
        - The first portion says a-z, meaning it's searching for any lowercased letter. 
        - The second portion says 0-9, this searches for any number within that range.
        - The _ and - indicate that these are both valid characters to search for.
        - As stated before, \. indicates that a period is a valid character to search for.
        - Finally, the + outside the bracket implies that there must be at least one character for this to be a valid search. 

    2. Domain
    `([\da-z\.-]+)`
        - The first portion \d indicates that it is looking for any digit. This is similar to 0-9.
        - The second portion is the same as above, a-z, searching for any lower cased letter.
        - Next we have the two special characters that are matches, . and -
        - Similar to above, + implies that there must be at least one character for this to be a valid search. 

    3. Extension
    `([a-z\.]{2,6})`
        - The first portion a-z searches for any lower cased number.
        - The second portion that . will be a match.
        - Lastly, we have an expression within {}. This signifies that the final block can only have from 2 to 6 characters. 

### Greedy and Lazy Match

Regex is considered a greedy system. This means it will look for as many opportunities of the desired string as possible. There are symbols we can use to get around this.

    A ? can be added after a quantifier to indicate to match as few times as possible. 

## Author

If you have any questions reguarding this project, a separate one, or just want to chat :

Github : marcielucke@github.com
LinkedIn : www.linkedin.com/in/marcella-lucke
Email : luckemarcella@gmail.com