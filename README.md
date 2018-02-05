<b>In This Application we can Export Jar for Classes.jar files of particular application/Project Jar files.</b>



app---build.gradle 
-------------------------

//task to delete the old jar


task deleteOldJar(type: Delete) {<br>
    delete 'build/libs/ramesh.jar'<br>
}


//task to export contents as jar


task exportJar(type: Copy) {<br>
    from('build/intermediates/bundles/release/')<br>
    into('release/')<br>
    include('classes.jar')<br>
    ///Give whatever name you want to give<br>
    rename('classes.jar', 'ramesh.jar')<br>
}<br>
exportJar.dependsOn(deleteOldJar, build)


After Editing the code As Mention About...
------------------------------------------

->Run the Project(Shift+F10).
->Select the Tab Gradile Projects, and then select app(Ctrl+Tab+G)
->app-->Tasks ---> other --> double click on export jar or run the export jar
->select the window tab project shortcut for android studio (Alt+1) make sure u selected Project from dropdown
->select release-->u can see ur jar file example: ramesh.jar file
