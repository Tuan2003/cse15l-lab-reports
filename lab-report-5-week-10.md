# **Lab Report 5 - Week 10**

So I to find the tests that produced the different results, I simply just ran.

`vimdiff file1.txt file2.txt`
___ 
This used the built in [powerful VIM editor](https://www.vim.org/) that easily showed how each file differs in a side by side comparison.

The image below is a small little snippet of the two files that I compared. 

![Image](/Images/vimdiff.png)

The left half is using the implementation that was provided by the TAs. The other half is the output using my implementation of markdown-parser. As we can easily see, there is a clear difference between my implementation, and the implementation provided for lab 9.
___
## **Test File 1** 

I have went ahead and decided to choose markdown file [567](https://github.com/TuannDang/markdown-parser/blob/main/test-files/567.md) as my first test file to compare based on what was provided after using vimdiff to compare the two side by side outputs. 

Below is a screenshot of the contents of [567.md](https://github.com/TuannDang/markdown-parser/blob/main/test-files/567.md). I have also decide to use the [Visual Studio Code](https://code.visualstudio.com/) preview as my way of determining which one is a link and which ones are not. 

![Image](/Images/567md%20contents.png)

As expected, we are not expecting any links to be returned. 

The screenshot below is what my implementation returned as an output: 

![Image](/Images/MyImplementation567ResultMD.png)

- As we can see my implementation returned the incorrect output. 

Now to compare this to the implementation provided for Lab 9:

![Image](/Images/Lab9-567MDResult.png)

- As expected, the implementation provided in Lab 9 produced the correct output that we were looking for. 

### **Bug?**
![Image](/Images/CodeChangeMyImplementation.PNG)

- So, I think the bug here, causing my implementation to produce the wrong output, is that my implementation does not take into consideration spaces in links, which causes it to produce the incorrect input. So I would need to add several lines of code to check for empty spaces within the link. 

___
## **Test File 2**
As for the next test file I will be comparing against my implementation and the implementation provided in Lab 9 is [578.md](https://github.com/TuannDang/markdown-parser/blob/main/test-files/578.md).

Also provided below is a screenshot of the contents of [578.md](https://github.com/TuannDang/markdown-parser/blob/main/test-files/578.md). 

![Image](/Images/578md%20contents.png)

- As provided by the Visual Studio Code preview above, we are not expecting any links to be returned because the preview only has an image. 

The screenshot below is what my implementation returned as an output: 

![Image](/Images/MyImplementation578ResultMD.png)

- Unfortunately, my implementation produced the incorrect output that we were looking for. 

Let's go ahead and check out what the implementation provided for Lab 9 produced! 

![Image](/Images/Lab9-578MDResult.png)

- Looks like the implementation provided for Lab 9 produced the correct result that we were looking for. 

### **Where is the bug?**
![Image](/Images/CodeChangeMyImplementation.PNG)
- As for the bug, it looks like something is wrong with my getLinks() method. In order to fix this issue so that it produces the correct result, I need to check for instances where there are images in a markdown file. Specifically, I need to search for when there are consecutive instances of `![]()` describing that there is an image. This will require myself to fix the getLinks() method so that it ignores images. 
