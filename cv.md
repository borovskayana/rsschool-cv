<h1>Frontend Developer</h1>
<img src="https://scontent-waw1-1.xx.fbcdn.net/v/t39.30808-6/268278753_1707562029635046_1690469163495826927_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=8bfeb9&_nc_ohc=ujuHZR0GUN4AX8hyvIp&_nc_ht=scontent-waw1-1.xx&oh=00_AfC4890mhvtiZntIXsw8DXDQebxWEcrdlzIV4Y1hZduM5Q&oe=63987BC5">
<h1>Yana Borovska</h1>
<p>+48 698 799 885</p>
<h2>Briefly About Myself:</h2>
<p>25-year-old web developer from Kyiv, Ukraine, now based in Gdansk, Poland. Successfully finished: professional course of web development knowledge: HTML, CSS, JavaScript, React); professional course of 3D Artist Software knowledge (Autodesk Maya, Substance painter, Marmoset Toolbag, Adobe Photoshop). I always look at the latest design trends to add insight, creation, motivation, and innovation.</p>
<h2>Skills and Proficiency:</h2>
<p>Languages: HyperText Markup Language (HTML); Cascading Style Sheets (CSS); JavaScript (JS). Libraries: React; jQuery; Redux. </p>
<h3>Courses:</h3>
<p>Johns Hopkins University: HTML, CSS, JavaScript for Web Developers.</p> 
<p>Johns Hopkins University: Single Page Web Aplications with AngularJS.</p>
<p>Academind by Maximilian Schwarzmüller: React - The Complete Guide (incl Hooks, React Router, Redux)</p>
<h2>Projects</h2>
<a href="https://borovskayana.github.io/my-site/site/">My personal site</a> 
<h3>Code example:</h3>
<p>Interactive whiteboard</p>



```
<const canvas = document.getElementById("canvas");
canvas.width = window.innerWidth - 100;
canvas.height = window.innerHeight * 0.6;
let context = canvas.getContext("2d");
context.fillStyle = "white";
context.fillRect(0, 0, canvas.width, canvas.height);
let restore_array = [];
let start_index = -1;
let stroke_color = 'black';
let stroke_width = "2";
let is_drawing = false;

function change_color(element) {
  stroke_color = element.style.background;
}

function change_width(element) {
  stroke_width = element.innerHTML
}

function start(event) {
  is_drawing = true;
  context.beginPath();
  context.moveTo(getX(event), getY(event));
  event.preventDefault();
}

function draw(event) {
  if (is_drawing) {
    context.lineTo(getX(event), getY(event));
    context.strokeStyle = stroke_color;
    context.lineWidth = stroke_width;
    context.lineCap = "round";
    context.lineJoin = "round";
    context.stroke();
  }
  event.preventDefault();
}

function stop(event) {
  if (is_drawing) {
    context.stroke();
    context.closePath();
    is_drawing = false;
  }
  event.preventDefault();
  restore_array.push(context.getImageData(0, 0, canvas.width, canvas.height));
  start_index += 1;
}

function getX(event) {
  if (event.pageX == undefined) {return event.targetTouches[0].pageX - canvas.offsetLeft}
  else {return event.pageX - canvas.offsetLeft}
  }


function getY(event) {
  if (event.pageY == undefined) {return event.targetTouches[0].pageY - canvas.offsetTop}
  else {return event.pageY - canvas.offsetTop}
}

canvas.addEventListener("touchstart", start, false);
canvas.addEventListener("touchmove", draw, false);
canvas.addEventListener("touchend", stop, false);
canvas.addEventListener("mousedown", start, false);
canvas.addEventListener("mousemove", draw, false);
canvas.addEventListener("mouseup", stop, false);
canvas.addEventListener("mouseout", stop, false);

function Restore() {
  if (start_index <= 0) {
    Clear()
  } else {
    start_index += -1;
    restore_array.pop();
    if ( event.type != 'mouseout' ) {
      context.putImageData(restore_array[start_index], 0, 0);
    }
  }
}

function Clear() {
    context.fillStyle = "white";
    context.clearRect(0, 0, canvas.width, canvas.height);
    context.fillRect(0, 0, canvas.width, canvas.height);
    restore_array = [];
    start_index = -1;
} >
```

<h2>Contact me:</h2>
<a href="https://www.linkedin.com/in/yana-borovska-615b771bb/">Linkedi</a> 
<br>
<p>E-mail: yanaboro123@gmail.com</p>
