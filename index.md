# Week 5 Lab Report: Researching Commands



 Student: ***[Ben Stirling](https://github.com/abenstirling)***
Professor: ***[Joe Politz](https://github.com/jpolitz)***
Date: ***9/29/22***

---

### Researching Commands

For this lab I will be inspecting the `grep` command. I found 3 interesting *command-line options,* and gave three examples for each of the types of commands. 

---

1. Recursive Searching With `grep`
    1. For our first three examples, we utilize the -r and -i tags which allow us to recursively search through several subdirectories and look inside each file for the search term, thick. 
    
        
        ```bash
        grep -r -i thick .
        ```
        
        The output can be seen below: 
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled.png)
        
        This is specifically useful for our application because there are a TON of files and in order to search INSIDE of them allows us to isolate only the files matching our term(s). 
        
    2. For our second example, we are searching for a term that has no matches. We are utilizing the same syntax as the previous command. 
    
        
        ```bash
        grep -r -i asdf .
        ```
        
        The output is below:
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%201.png)
        
        This is important to know that there is not necessarily a simple response from the command line that lets the user know that there is not a match. The only possible indicator is the red ‘X’ that could show that the command didn’t return any matches. Sometimes there might not be a term match, and now you can know what to look for. 
        
    3. For our third example, we are going to index with the recursive dereference option. The syntax is similar to above, we just changed it to the -R and the search term, xyz.
    
        
        ```bash
        grep -R -i xyz .
        ```
        
        The output can be seen below: 
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%202.png)
        
    
    This is extremely useful, because you can now index utilizing the symlinks in your search, which you were unable to do with just -r alone. 
    

---

1. Multiple Search Terms
    1. What if we had multiple variables or words we were looking for? 
        
        ```bash
        grep -E -w -i "hello|test" chapter-1.txt
        ```
        
        Below is the output for the command:
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%203.png)
        
        This is useful because we are able to index a file for two terms. You could imagine iterative loops where there might be two variables used to index. This could allow you to speed up that identification process. 
        
    2. For our second example, we are searching for a term that has no matches. We are utilizing the same syntax as the previous command. 
        
        
        ```bash
        grep -E -w -i "nada|aqui" chapter-1.txt
        ```
        
        Below is the output: 
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%204.png)
        
        Similar to the 1B example, we can see that there is no response. We do see that there is a red ‘X’ which should signify that our command was unsuccessful in finding any matches. This is useful for us to know what it looks like if we don’t have any catches. 
        
    3. For our third example, we are showing how you can search for any amounts of search terms. 
        
        
        ```bash
        grep -E -w -i "rip|nothing|jk" chapter-1.txt
        ```
        
        Below is the output: 
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%205.png)
        
        You can see that we added now three terms, “rip” and “nothing” and “jk”, to the search indexing. This allows us to search any amount of variables with one command. I could imaging that it is useful to search files to figure out which may use given functions or classes in Java. 
        

---

1. Including and Excluding Search terms
    1. For our first example, we are going to iscolate a certain file type using the `—include` term. 
        
        ```bash
        grep -R --include="*.txt" "foo" ./911report/
        ```
        
        Below is the output: 
        
        ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%206.png)
        
        This is incredibly useful because we are able to isolate a certain file type that we  might want to index. Say a .java file for example. We might not want to index all of the .git logs for a certain term.
        
    
    2. Conversely, let’s say we want to exclude a subset of a file system while searching! 
    
    ```bash
    grep -R --exclude="*.html" "foo" ./911report/
    ```
    
    For this example, I made a .html file and put a paragraph with the text “foo”. This allows us to test our exclude method if we are not looking for .txt files.
    
    Here is the result: 
    
    ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%207.png)
    
    This is just as useful as the include method as we are able to narrow down the focus of the command. It was satisfying that it worked first try with a totally different file type, .html. 
    
    3. Let’s use exclude and include together! 
    
    ```bash
    grep -R --include="*.txt" --exclude="*.html" "foo" ./911report/
    ```
    
    The result is below: 
    
    ![Untitled](Week%205%20Lab%20Report%20Researching%20Commands%20be99ae4fa87b45459794753570fa1ee0/Untitled%208.png)
    
    This can be extremely useful in cases that there are several file types with similar or same variable names. I think of this like toggling or filtering the total subset to save you time looking through the grep result. 
    

---

### In Summary…

I learned a tremendous amount about how to efficiently index large file systems utilizing `grep` and its complimentary commands that allow users to search for terms, files and combinations of both. 

Since I spend most of my time in the terminal, I will frequently be using all of the commands to be efficient with my time and programming methodologies.