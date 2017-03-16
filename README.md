# Learning-D3---Lesson---1
Understanding what D3 is and understanding very basic commands like select, append, enter and attempting to draw a simple bar graph with random data taken

Step 1:
Creating a localhost server as it is advised to launch HTML file with a local host server URL than file path for the D3 js code to function correctly.
Let me start with the ways to host a folder as server using Node.JS before going through the fundamentals of D3.JS.
Install Node.JS and copy the following code would in the command prompt helps in making a folder as a host to local server.
npm install -g http-server
http-server &

Now we have successfully started a server and we can see the links appearing in the command prompt which helps in launching the HTML file in browser

D3 Basics:
Download Latest D3.JS file from GitHub and add the file as script in HTML file
<script type = "text/javascript" src = "d3.js"> </script>

Now check below the code to develop a bar graph for 25 entries using D3.Js
<script type="text/javascript">
   (For Assigning Random 25 values to a array variable called Dataset)
        var dataset = [];  
        for (var i =0;i <25;i++)
        {
          var NewNumber = Math.random() *30;
          dataset = dataset.concat(NewNumber);
        }
        
            d3.select("body").selectAll("div")  (To select tag "Body" and all "div" tags under it)
              .data(dataset)                    (To gather the data in dataset array, from next step onwards code runs in iterative way                                                 for every element of data)
              .enter()                          (If the div tags are lesser than elements of Data, it creates placeholders for the left                                                 out things)
               .append("div")                   (To cretae div tags in the placeholders created)
              .attr("class","bar")              (To add attribute class = "bar" which has been defined in the CSS - Which created bar                                                   diagrams)
              .style("height",function(d)       (To add style height which is dynamic to each element value. function(d) takes that                                                      element of the data according the iteration as input and returns teh computed value)
                      {return d*5 + "px";}
                    );
        </script>
        
        
        
        
