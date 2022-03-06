# Week 8 Lab Report 4 - CSE15L

## Links
- *[my markdownparse](https://github.com/wgascarosas/markdown-parse)*
- *[reviewed markdownparse](https://github.com/w2llS/markdown-parse)*

# Snippet 1
Using *[this](https://github.com/wgascarosas/markdown-parse)* cite, Snippet 1 should produce the following... 
![image](snippet1code.png)

## Testing
From the code produced above we can see that only one link gets produced. This corresponds to *another link* contaning *'google.com*. 
Here is the test I implemented...
![image](snippet1-test.png)

Here are the results when ran with my markdownparse
![image](snippet1-myrepo.png)

Here are the results when ran with the reviewed markdownparse
![image](snippet1-otherrepo.png)

# Snippet 2
Using *[this](https://github.com/wgascarosas/markdown-parse)* cite, Snippet 2 should produce the following... 
![image](snippet2code.png)

## Testing
From the code produced above we can see that three links gets produced. This corresponds to *nested link* contaning *a.com*, *a nested parenthesized url* contaning *a.com(())*, and *some escaped [ brackets ]* contaning *example.com"*.
Here is the test I implemented...
![image](snippet2-test.png)

Here are the results when ran with my markdownparse
![image](snippet2-myrepo.png)

Here are the results when ran with the reviewed markdownparse
![image](snippet2-otherrepo.png)


# Snippet 3
Using *[this](https://github.com/wgascarosas/markdown-parse)* cite, Snippet 3 should produce the following... 
![image](snippet3code.png)

## Testing
From the code produced above we can see that only one link gets produced. This corresponds to *this title text is really long and takes up more than one line* contaning *https://ucsd-cse15l-wi22.github.io/*. 
Here is the test I implemented...
![image](snippet3-test.png)

Here are the results when ran with my markdownparse
![image](snippet3-myrepo.png)

Here are the results when ran with the reviewed markdownparse
![image](snippet3-otherrepo.png)

# Question Responses
*Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.*

**Answer**: 
I think in order to make the program work for inline code with backticks it would be a more involved change. In order to make the test pass for this we would most likley need an if statements that will ignore the backticks. We could also just remove any backticks but this would again be more involved. 

*Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.*

**Answer**: 

*Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.*

**Answer**: 