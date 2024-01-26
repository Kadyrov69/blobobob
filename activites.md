---
title: "Activités"
order: 1
in_menu: true
---
<div class="glowy-blob">
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
</div>

<span>Drag</span>

<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
  <defs>
    <filter id="goo">
      <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
      <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -9" result="goo" />
      <feComposite in="SourceGraphic" in2="goo" operator="atop"/>
    </filter>
  </defs>
</svg>



<script>
var doms = document.getElementsByClassName("glowy-blob");

var selected = 0;

for(var x =0;x<doms.length;x++) {
    for(var i = 0;i<doms[x].children.length;i++) {
        doms[x].children[i].addEventListener("mousedown", function(e){
            selected = this;
        })
    }
}

window.addEventListener("mouseup", function(e){
  selected.style.animation = "bounceback 1s ease";
  selected.style.animationFillMode = "forwards";
  var lala = selected;
  selected = null;

  setTimeout(function() {
      lala.style.animation = "";
      lala.style.animationFillMode = "";
      lala.style.left = "";
      lala.style.top = "";
  },1000)

})

window.addEventListener("mousemove", function(e) {
    if(selected == null || !selected) return;
    selected.style.left = (e.clientX - (selected.getBoundingClientRect().width/2) - window.innerWidth/2) +"px"
    selected.style.top = (e.clientY - (selected.getBoundingClientRect().height/2) - window.innerHeight/2 ) +"px"
    selected.style.animation = 0;
}) </script> 