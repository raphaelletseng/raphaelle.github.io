---
layout: post
title: "Notebook Doodles (and some CSS/ JavaScript fiddling)"
date: 2021-02-05
tags: art web-dev personal
---

I've been keeping notebooks as journals / agendas / sketchbooks etc. for over six years now. They act as places where I can make endless lists, doodle, write, and brainstorm.
I'm coming towards the end of the one I've had since October 2019, and I wanted to compile all the little drawings I've haphazardly done in the margins and over notes. Often,
I'll study artists and illustrators that I admire, so I can't claim anything here for my own. I'll also occasionally draw from pinterest images or just my imagination.

Some artists / illustrators I very much enjoy and owe credit to:
- [Chris Riddell](https://www.instagram.com/chris_riddell/)
- [Leigh Ellexson](https://www.instagram.com/leighellexson/)
- [Cheyenne Barton](https://www.instagram.com/chey.barton/)
- [Minnie Small](https://www.instagram.com/minniesmall/)

---

This was also a useful exercise in practicing with JavaScript and CSS. Some notes:
1. Ids (#) for elements can be useful for things other than just styling. They can be used to call functions and to single out parts of a page.
2. Turns out you can chuck a whole bunch into markdown which is really nice.
3. If something is resulting in null, you might have to wrap it in a `<body>` tag.

The basis of this image gallery is taken from [here](https://www.w3schools.com/howto/howto_css_image_grid_responsive.asp).

---
<html>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
*{box-sizing: border-box;}
/*---- Blog post: Notebook Doodles ---*/
.doodle-row{
  display: -ms-flexbox;
  display:flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  padding: 0 4px;
}

.doodle-column{
  -ms-flex:25%;
  flex:25%;
  padding: 0 4px;
}

.doodle-btn{
  border: none;
  outline: none;
  border-radius: 4px;
  padding: 10px 16px;
  background-color: #D2F3F8;
  cursor: pointer;
  font-size: 18px;
}
.doodle-btn:hover{
  background-color: #888;
}

.doodle-btn.active{
  background-color: #65C7BC;
  color: white;
}

.Buttons{
  margin:auto;
  padding: 10px;
  box-sizing: border-box;
  text-align: center;
}

img{
  border-radius: 4px;
  padding: 2px;
}

</style>

<body>

<div class ="Buttons" id="myButtons">
  <button class="doodle-btn" onclick="one()">1</button>
  <button class="doodle-btn" onclick="two()">2</button>
  <button class="doodle-btn active" onclick="four()">4</button>
</div>

<!--- Photo Grid ----->
<div class="doodle-row">
  <div class="doodle-column">
    <img src="/assets/notebook-doodles-1/IMG_20210205_122336.jpg" alt="Doodle 1" style="width:100%">
    <img src="/assets/notebook-doodles-1/IMG_20210205_122416.jpg" alt="Doodle2" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_122503.jpg" alt="Doodle3" style="width:100%">
    <img src="/assets/notebook-doodles-1/IMG_20210205_122635.jpg" alt="Doodle4" style="width:100%">
    <img src="/assets/notebook-doodles-1/IMG_20210205_122717.jpg" alt="LangLeav Doodle" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_122752.jpg" alt="leighTigers" style="width:100%">
    <img src="/assets/notebook-doodles-1/IMG_20210205_122902.jpg" alt="NorwegianWoodDoodle" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123138.jpg" alt="midori" style="width:100%">
  </div>


  <div class="doodle-column">
    <img src="/assets/notebook-doodles-1/IMG_20210205_122828.jpg" alt="Doodle5" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123008.jpg" alt="planner" style="width:100%">
    <img src="/assets/notebook-doodles-1/IMG_20210205_123101.jpg" alt="travel doodles" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123210.jpg" alt="doodle-minismall" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123237.jpg" alt="thanksgiving-doodle" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123300.jpg" alt="nose&lips" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123337.jpg" alt="riddell-mood" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123450.jpg" alt="cBarton-mushroomMan" style="width:90%">

  </div>

  <div class="doodle-column">
    <img src="/assets/notebook-doodles-1/IMG_20210205_123421.jpg" alt="riddell-dragon" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123518.jpg" alt="twoSum-dragon" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123547.jpg" alt="data structures" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123635.jpg" alt="unfinished-dragon" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123706.jpg" alt="red-girl" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123739.jpg" alt="2020-spread" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123812.jpg" alt="riddell-inspo" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123904.jpg" alt="soul-eater" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124356.jpg" alt="a weird blue cat" style="width:85%">

  </div>

  <div class="doodle-column">

    <img src="/assets/notebook-doodles-1/IMG_20210205_123942.jpg" alt="cuddle-keeper" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124022.jpg" alt="dream catcher" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124331.jpg" alt="Riddell Study" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124058.jpg" alt="fate spirit" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124123.jpg" alt="vagina-power" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124148.jpg" alt="nonbinary mages" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124211.jpg" alt="im blooming owl" style="width:100%">

    <img src="/assets/notebook-doodles-1/IMG_20210205_124238.jpg" alt="blueberry head" style="width:100%">

  </div>


</div>

<script>


var elements = document.getElementsByClassName("doodle-column");
var i;
function one(){
  for (i = 0; i < elements.length; i++){
    elements[i].style.msFlex="80%";
    elements[i].style.flex="80%";
  }
}

function two(){
  for(i=0; i<elements.length;i++){
    elements[i].style.msFlex = "50%";
    elements[i].style.flex="50%";
  }
}

function four(){
  for(i=0; i<elements.length; i++){
    elements[i].style.msFlex = "25%";
    elements[i].style.flex = "25%";
  }
}

var Buttons = document.getElementById("myButtons");
var btns = Buttons.getElementsByClassName("doodle-btn");

for(var i = 0; i < btns.length; i++){
  btns[i].addEventListener("click", function() {
    var current = document.getElementsByClassName("active");
    current[0].className= current[0].className.replace(" active", "");
    this.className += " active";
  });
}

</script>
</body>




<link rel="stylesheet" href="https://raphaelletseng.github.io/raphaelletseng.github.io/assets/css/index.css">
