# Title Case Converter
<span><img src="https://img.shields.io/badge/Adobe%20XD-470137?style=for-the-badge&logo=Adobe%20XD&logoColor=#FF61F6" /> </span> 
<span><img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" /> </span> 
<span><img src="https://img.shields.io/badge/Sass-CC6699?style=for-the-badge&logo=sass&logoColor=white" /> </span> 
<span><img src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E" /> </span>

Title case is a style that is used for the titles of articles, books, movies, songs, and other works. It makes the title look elegant and readable.
Live app ➡️ https://maciejkuran.com/title-case-converter

In the example below, I don't access any DOM elements. It's just a pure function.

If you're interested in checking my application source code, feel free to dive deeper into uploaded files.

## Introduction
In this case study, I am writing the function that does title case converting. However, there's a trick.

All major words will be capitalized, while minor words will be lowercased. It means that we capitalize every word except articles, coordinating conjunctions, and others. In my program, I called them 'specialWords'. The special words are saved in the array below.

```
const specialWords = ['and','an','a','or','the','is','of', 'but','on',];
```
So what does this application do? Please check the example below.

INPUT: The man of the forest.
OUTPUT: The Man of the Forest.

## Javascript concepts
To write this application, I am going to use string and array methods. First of all, we need to convert an input value to lowerCase(). Then I split() the string, which means I convert it to an array.

I loop through this array, checking if the 'specialWords' array includes() any specific 'word' from our array (our input string that I converted). If it does, this specific 'word' will be toLowerCase(), if it doesn't, the first character of each word will be converted to upperCase(). Then I convert back the 'output' array to a string with the join() method.

The 'correctOutput' function is the callback function. This function generally corrects the final output but is also called in the ternary operator. Let me explain what it does.

If our input string starts from any of the special words e.g. 'the', our output will be:

the Beginning of the Road, instead of The Beginning of the Road

That's what this function is for. We return this function, passing 'output' – as the argument.

This function will always convert the first index(0) of our output string to upperCase(), no matter if it's a special word, or not.

```
const convertString = string => {
const correctOutput = output => output.at(0).toUpperCase() + output.slice(1);

const output = string
.toLowerCase()
.split(' ')
.map(word => (specialWords.includes(word) ? word : correctOutput(word)))
.join(' ');

return correctOutput(output);
};

console.log(convertString('The best of the best')); // The Best of the Best
console.log(convertString('The beginning of the road')); //The Beginning of the Road
```

## UI App Design
![Zasób 2](https://user-images.githubusercontent.com/103118542/172853147-c2fc60f9-5b3e-4dfc-987f-a80ba0cc8e5f.png)



## Functionality
- convert function
- clear/reset window function
- copy output to clipboard function

Live app ➡️ https://maciejkuran.com/title-case-converter
