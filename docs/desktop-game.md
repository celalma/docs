    I know how to do it, the only problem is that it requires transparent project background, and as I know 
    Turbowarp doesn't support it. However, other scratch mods can do it, I've tested in Penguinmod and it worked, 
    now you only need to make the background transparent (it is white by default). I've just took the block for 
    background color from some camera extension, added it to a separate extension and just set color alpha to 0.
    
    Then, when you have a project with transparent background: after packaging into Electron for windows, 
    you can go to "root folder/resourses/app" and open "electron-main.js". Inside it, find function "const 
    createProjectWindow" and in "const options" add lines "transparent: true, frame: false, alwaysOnTop: true, 
    minimizable: false, resizable: false" and delete "backgroundColor: "#000000"" line. It's easy to figure out 
    what those parameters do, don't forget to save the file. There also a parameter that makes the window clickable 
    through, you can find it in Electron docs online. Also you need to go to "root folder/resourses/app" and open 
    "index.html". In the beggining of the file there are CSS code. Find ":root, body.is-fullscreen {" and inside 
    it change "background-color: #000000" to "background-color: transparent". That makes HTML background transparent. 
    Of course save the files after editing. After that, everything should work, screenshot attached

<sub>Posted by [Shoorsh (u/No_Health_1422)](https://www.reddit.com/user/No_Health_1422/) on [Reddit](https://www.reddit.com/user/No_Health_1422/).  
See [original post](https://www.reddit.com/r/turbowarp/comments/1tt3khr/how_could_one_overlay_a_project_over_the_whole/).</sub>
