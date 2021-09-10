******************************************************************************
******************************************************************************
Build a PWA(Progressive Web Application) that allows users to do the following for a set of random objects positioned on a map, 
the map can be as simple as an SVG HTML Image, a WebGL rendered object, or an actual geographical map.

Functionality:
    Add/Update/Delete Config
    View streaming data

The data model should contain the following structures:
    Object Configuration: Contains data like (Id, title, location-, and a bunch of dynamic properties)
    Object Real-time Data: The corresponding object will be sending streaming data at a cadence of ~500 ms
 
Project components: 
    Web frontend: You can use any off the shelf component framework (Material UI, ant.design…)
    Form based component to add/update/delete the object configuration
    Realtime component to show streamed data
    Backend (Any language of choice, Nodejs/Python/Go …)
    Add/Update/Delete Object Configuration (REST)
    Stream Object Data (Websockets), potentially build a simple simulation component so that you can test your UI
    Database (Any SQL/NoSQL DBMS would be ok)
    Bonus: Infrastructure components (Docker, Docker-Compose, even kuberenetes…)
    Bonus: Set Location on the map by moving the object
    Bonus: Webgl based 3D UI for showing the actual 3d models of the objects + data overlay, using something like threejs (You can find low poly 3d models on sketchfab or ploy)
    Bonus: Send a Web Notification if streamed data go beyond a certain threshold
 
Some Considerations: 
    The project needs to be delivered the day before your interview day.
    The project has to be delivered as a git controlled folder, the code is yours, so you can choose to put it on github and give us access to it, or just give it to us as a shared folder.
    We will be only testing on Chrome
    You can send any questions you might have, we will be replying ASAP
******************************************************************************
******************************************************************************


Project Ideas:
    Frontend Utilizing ReactJS for live updates on data
        - To get object data, websocket connection with NodeJS server to update current data displayed 
        - To add, remove, update a new object with new config utilize a REST POST Requst to Backend server
    
    Backend NodeJS with Express and MongoDB
        - MongoDB will hold a document for each "random object" and it's configuration
            -Configuration includes ID, title, location by default, dynamic adding of additional data
        
        - MongoDB will also contain one document with a list of all active objects and their configurations.
            - Generated by the configuration MongoDB

        - Websocket connection that will send back data for active objects.
            - Websocket function will call MongoDB to get active object data
        
        - Request functions to add, remove, and update configurations

    Python Simulation script that will randomly change and modify object attributes.


Example Object:

    object0 = {
        id: 0,
        title: Optimus,
        location: {x: 24, y:32, z:45},
        state: "Walking",
        speed: 5,
        color: [255, 255, 255]
    }

    object1 = {
        id: 0,
        title: CyberTruck,
        location: {x: 80, y:50, z:2},
        state: "Parked",
        isLocked: false,
        speed: 0,
        color: [45, 45, 45]
    }
