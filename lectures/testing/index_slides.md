layout: true
class: center, middle
name: pic
background-size: contain

---
layout: true
class: center, top
name: fragment

.title[{{name}}]

---
layout: true
class: center, middle
name: base

.title[{{name}}]



---
name: blank page


```html
<div>code</div>
```
<div>html</div>

???
* foo


---
name: dynamic typing

<div 
  class="codepen hidden" markdown="0"
  data-prefill='{
    "stylesheets": ["//cs52.me/assets/css/codepen-mods.css"],
    "scripts": ["//cs52.me/assets/codepen-mods.js"]
  }'
  data-preview="true"
  data-height="400" 
  data-theme-id="24117"
  data-default-tab="js,result"
  data-user="timofei"
  data-editable="true"
>
<pre data-lang="babel">
var i;
// console.log(i, typeof(i));
i = 32;
// console.log(i, typeof(i));
i = 'foobar';
// console.log(i, typeof(i));
i = true; 
// console.log(i, typeof(i));
</pre>

</div>

* have type of the last thing assigned
* primitive types: `undefined`, `number`, `string`, `boolean`, `function`, `object`


???
* variables aren't assigned a type
* but values do have a type

---
name: closure and scope

<div 
  class="codepen" markdown="0"
  data-prefill='{
    "stylesheets": ["//cs52.me/assets/css/codepen-mods.css"],
    "scripts": ["//cs52.me/assets/codepen-mods.js", "https://code.jquery.com/jquery-2.2.4.min.js"]
  }'
  data-preview="true"
  data-height="550"
  data-default-tab="js,result"
  data-theme-id="24117"
  data-user="timofei"
  data-editable="true"
>
<pre data-lang="html">
  <blockquote>
    <div id="speech"></div>
    <div class="arrow bottom right"></div>
  </blockquote>
  <div id="cat">😼</div>
  <button id="go">hi cat!</button>
</pre>
<pre data-lang="css">
#cat {
  margin-top: 0.3em;
  font-size: 8em;
}

button {
  background: #0a0;
  color: white;
  margin-left: 2em;
  border-radius: 0.2em;
  border-width: 0.0em;
  padding: 0.2em 3em;
  font-size: 2em;
}


blockquote {
  background-color: #f8f8f8;
  border: 2px solid #c8c8c8;
  border-radius: 1em;
  height: 1.5em;
  width: 22em;
  text-align: center;
  padding: 20px;
  position: relative;
}

blockquote .arrow {
  border-style: solid;
  position: absolute;
}

.bottom {
  border-color: #c8c8c8 transparent transparent transparent;
  border-width: 13px 13px 0px 13px;
  bottom: -13px;
}

.bottom:after {
  border-color: #f8f8f8 transparent transparent transparent;
  border-style: solid;
  border-width: 13px 13px 0px 13px;
  bottom: 2.8px;
  content: "";
  position: absolute;
  left: -12.5px;
}

</pre>
<pre data-lang="babel">
function go() {
  const messages = ["Meow!", "I'm a talking cat!", "Callbacks are fun!"];

  for (var i = 0; i < messages.length; i++) {
    setTimeout(function () {
      cat.say(`${messages[i]} ${i}`);
    }, i * 1500);
  }
  
  // alias i or
  // use let or

  /*
  messages.forEach( (message, i) => {
    setTimeout(function () {
      cat.say(`${message} ${i}`);
    }, i * 1500);
  });
  */

}



// from: https://hacks.mozilla.org/2015/07/es6-in-depth-let-and-const/



let cat = {
  speech: $("#speech"),
  cat: $("#cat"),
  say: function(quip) {
    this.speech.html(quip);
    this.cat.html("😸");
    setTimeout( function() {
      this.speech.html("");
      this.cat.html("😼");
    }.bind(this), 1250);
  }
};

$("#go").on("click", function () { go(); });</pre>

</div>


<!-- <p data-height="435" data-theme-id="24117" data-slug-hash="f2e5b9149a019b953859e6de0af83f54" data-default-tab="js,result" data-user="timofei" data-embed-version="2" data-editable="true" class="codepen">See the Pen <a href="http://codepen.io/timofei/pen/f2e5b9149a019b953859e6de0af83f54/">talking cat var scoping problem</a> by Tim Tregubov (<a href="http://codepen.io/timofei">@timofei</a>) on <a href="http://codepen.io">CodePen</a>.</p>
 -->

