- **Metadata**
- [[Personal]]
- [[Code]] 
- [[Twitter]]
- [[Chrome Extensions]]
- Summary: Chrome extension to link primary sources to tweets


- MVP: Simple chrome extension that provides a link to a primary source to any given tweet

- {{[[kanban]]}}
    - TODO
        - Build out chrome extension to appear only on twitter domain
        - "Activate" extension for a given tweet - think about how to do this. Right clicking or something like on hover?
        - see if it's possible to make api calls from the extension - should be
        - Build minimal backend which stores tweet -> primary source reference locally
        - Move local backend to aws or something similar 
        - Release 
        - ~~Think about how to propagate the information downward so that replies to a tweet are attached to a primary source~~
    - DOING
        - Create repo with minimal set of files for chrome extension
    - DONE
- MVP Ideas
    - 'Base Truth': if there is no attached primary source just use google search for key terms? 
        - How do you identify key terms?
            - Resource - https://monkeylearn.com/keyword-extraction/
            - 
