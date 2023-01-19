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
  background-color: #ffffff;
  border-radius: 6px;
  transform: rotateY(180deg);
}
.back {
  background-color: #ffffff;
  border-radius: 6px;
  width: 100px;
  height: 100px;
  margin-top: auto;
  margin-bottom: auto;
}
img {
  border-radius: 6px;
}
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(4, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 60px;
}
</style>
</head>
<body>
<body>
  <div class="grid-container">
    <div class="flip-card" id="card1">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="back" id="img-load"></div>
      </div>
    </div>
      <div class="flip-card" id="card2">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card3">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card4">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card5">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card6">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card7">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card8">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card9">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card10">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card11">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card12">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card13">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card14">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
        <div class="flip-card" id="card15">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
    <div class="flip-card" id="card16">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div id="img-load"></div>
      </div>
    </div>
  </div>
<script>
  const flipCard1 = document.getElementById("card1");
  const flipCard2 = document.getElementById("card2");
  const flipCard3 = document.getElementById("card3");
  const flipCard4 = document.getElementById("card4");
  const flipCard5 = document.getElementById("card5");
  const flipCard6 = document.getElementById("card6");
  const flipCard7 = document.getElementById("card7");
  const flipCard8 = document.getElementById("card8");
  const flipCard9 = document.getElementById("card9");
  const flipCard10 = document.getElementById("card10");
  const flipCard11 = document.getElementById("card11");
  const flipCard12 = document.getElementById("card12");
  const flipCard13 = document.getElementById("card13");
  const flipCard14 = document.getElementById("card14");
  const flipCard15 = document.getElementById("card15");
  const flipCard16 = document.getElementById("card16");
  flipCard1.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
    flipCard2.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard3.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard4.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard5.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard6.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard7.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard8.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard9.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard10.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard11.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard12.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard13.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard14.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard15.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard16.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
var images = [
 "/images/aw.png",
  "/images/dc.png",
  "/images/fp.png",
  "/images/gh.png",
  "/images/p.png",
  "/images/html.png",
  "/images/so.png",
  "/images/vs.png"
];
var randomImage = images[Math.floor(Math.random() * images.length)];
console.log(randomImage);
var image = "<img src='" + randomImage + "'>";
document.getElementById("img-load").innerHTML = image;
</script>