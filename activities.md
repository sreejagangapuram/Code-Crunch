# Mani: 
> Page for planning/ keeping track of work (or whatever else you'd like)

## Current Assignments: 
- Cards Game

## JSON/jQuery Notes for later

### General

1. First, you'll need to create an HTML table on your website where you want to display the scores. You can do this using standard HTML table elements, such as `<table>`, `<tr>`, and `<td>`.

2. Next, you'll need to retrieve the highest scores data from your backend system. This data is usually stored in a database, and you can use a server-side language (e.g., PHP, Python, Ruby) to query the database and retrieve the data. The server-side script should then encode the data in JSON format and return it to the client (your website).

3. Once the data is returned to the client, you can use jQuery to parse the JSON data and display it on the HTML table. You can do this by making an AJAX (Asynchronous JavaScript and XML) request to the server-side script and using the $.getJSON method to retrieve the JSON data.

4. Finally, you can use jQuery to append the data to the appropriate cells in the HTML table. You can use the .append() method to add the data as a new child element to the table cells.
Method 1:

### Step 3

#### Method 1

To retrieve the JSON data from the server-side script, you can use an AJAX request. AJAX allows you to make requests to the server and update a specific part of the webpage without reloading the entire page.

Here's an example of how you can make an AJAX request using jQuery:


`$.ajax({`
  `url: 'server-side-script.php',`
  `dataType: 'json',`
  `success: function(data) {`
    `// data contains the JSON data returned by the server`
  `}`
`});`

#### Method 2

You can also use the $.getJSON method, which is a shorthand for making an AJAX request and expecting a JSON response:

`$.getJSON('server-side-script.php', function(data) {`
  `// data contains the JSON data returned by the server`
`});`

In both examples, the server-side-script.php file is the server-side script that retrieves the data from the database and returns it in JSON format.

### Step 4

Once you have the JSON data, you can use jQuery to append it to the HTML table. Here's an example of how you can do this:

`$.getJSON('server-side-script.php', function(data) {`
  `// Iterate through the data and append it to the table`
  `$.each(data, function(index, item) {`
    `$('#table-body').append(`
      `'<tr>' +`
        `'<td>' + item.name + '</td>' +`
        `'<td>' + item.score + '</td>' +`
      `'</tr>'`
    `);`
  `});`
`});`

In this example, `#table-body` is the ID of the `<tbody>` element in the HTML table, and `item.name` and `item.score` are the name and score of the player, respectively.

## Game Research

**Logos:** Github, Stack Overflow, Discord, VS Code, Amazon Servers, Fastpages, Python, HTML

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  font-family: Arial, Helvetica, sans-serif;
}

.flip-card {
  background-color: transparent;
  width: 100px;
  height: 100px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}
.flip-card-inner.flip {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #800000;
  border-radius: 6px;
  border-color: #FFFFFF
  color: black;
}

.flip-card-back {
  background-color: #2980b9;
  border-radius: 6px;
  transform: rotateY(180deg);
}

img {
  border-radius: 6px;
}

</style>
</head>
<body>
<div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <img src="{{site.baseurl}}/images/istockphoto-951249780-612x612.jpg" alt="Avatar" style="width:100px;height:100px;">
    </div>
    <div class="flip-card-back">
      <img src="{{site.baseurl}}/images/GitHub-Mark.png" alt="Avatar" style="width:100px;height:100px;">
    </div>
  </div>
</div>
<script>
    document.querySelector('.flip-card').addEventListener('click', function() {
      this.querySelector('.flip-card-inner').classList.toggle('flip');
    });
</script>
</body>
</html>