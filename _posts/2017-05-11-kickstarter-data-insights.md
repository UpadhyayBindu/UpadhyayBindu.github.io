Aim of the project: Use html and d3.js to visualise data. 

Dataset: I picked the dataset for the month of March 2017 from [here](https://webrobots.io/kickstarter-datasets/). 

The csv folder had 44 csv files. I picked the first one to clean and see how the data looks. Based on the column headers, I made a sketch of the graphs and metrics that I would like to visualise. This enabled me to finalise the kind of visualisations that I would need. 

Metrics that interested me:
1. Goal amount
2. Pledged amount (amount raised)
3. Currency conversion to USD
4. Number of backers
5. Number of days the campaign was active 
6. Title of the campaign
7. Brief description

Initial plan: 
1. A scatter plot of goal amount vs pledged amount
2. A scatter plot of number of backers vs Success Measure. Success Measure = Pledged amount/goal amount
3. Word cloud of the titles
4. Word cloud of description

With the above plan, I first made a scatterplot for the data from the first csv. Once I got this to work, the challenge was to scale this with all the data that I had. (840 MB)

I used R to merge these 44 csv sheets into one. I further made another dataset with just 3 metrics that I needed for the first graph: goal amount, pledged amount, currency conversion rate (static). This helped to perform operations quicker on my computer. 

At this point, I wanted to see how many campaigns raised more than what they expected. 

Here is the graph:

<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="Content-type" content="text/html; charset=utf-8">
    <title>Testing Pie Chart</title>
    <script type="text/javascript" src="http://mbostock.github.com/d3/d3.js?2.1.3"></script>
    <script type="text/javascript" src="http://mbostock.github.com/d3/d3.geom.js?2.1.3"></script>
    <script type="text/javascript" src="http://mbostock.github.com/d3/d3.layout.js?2.1.3"></script>

    <style type="text/css">
        .slice text {
            font-size: 16pt;
            font-family: Arial;
        }
    </style>
  </head>
  <body>
    <script type="text/javascript">

    var w = 600,                        //width
    h = 600,                            //height
    r = 200,                            //radius
    color = d3.scale.category20c();     //builtin range of colors

    data = [{"label":"Above goal", "value":76805, "color": red},
            {"label":"Below goal", "value":96221}];

    var vis = d3.select("body")
        .append("svg:svg")              //create the SVG element inside the <body>
        .data([data])                   //associate our data with the document
            .attr("width", w)           //set the width and height of our visualization (these will be attributes of the <svg> tag
            .attr("height", h)
        .append("svg:g")                //make a group to hold our pie chart
            .attr("transform", "translate(" + r + "," + r + ")")    //move the center of the pie chart from 0, 0 to radius, radius

    var arc = d3.svg.arc()              //this will create <path> elements for us using arc data
        .outerRadius(r);

    var pie = d3.layout.pie()           //this will create arc data for us given a list of values
        .value(function(d) { return d.value; });    //we must tell it out to access the value of each element in our data array

    var arcs = vis.selectAll("g.slice")     //this selects all <g> elements with class slice (there aren't any yet)
        .data(pie)                          //associate the generated pie data (an array of arcs, each having startAngle, endAngle and value properties)
        .enter()                            //this will create <g> elements for every "extra" data element that should be associated with a selection. The result is creating a <g> for every object in the data array
            .append("svg:g")                //create a group to hold each slice (we will have a <path> and a <text> element associated with each slice)
                .attr("class", "slice");    //allow us to style things in the slices (like text)

        arcs.append("svg:path")
                .attr("fill", function(d, i) { return color(i); } ) //set the color for each slice to be chosen from the color function defined above
                .attr("d", arc);                                    //this creates the actual SVG path using the associated data (pie) with the arc drawing function

        arcs.append("svg:text")                                     //add a label to each slice
                .attr("transform", function(d) {                    //set the label's origin to the center of the arc
                //we have to make sure to set these before calling arc.centroid
                d.innerRadius = 0;
                d.outerRadius = r;
                return "translate(" + arc.centroid(d) + ")";        //this gives us a pair of coordinates like [50, 50]
            })
            .attr("text-anchor", "middle")                          //center the text on it's origin
            .text(function(d, i) { return data[i].label; });        //get the label from our original data array

    </script>
  </body>
</html>





