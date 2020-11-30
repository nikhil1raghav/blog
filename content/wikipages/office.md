+++
title="Minimal office suite"
description="Using browser and basic html capabilities for a workable office environment"
author="Nikhil"
+++

#### 1. Text editor
- Bookmark this or try pasting this for an instant text editor.
```html
data:text/html,<html contenteditable>
```
- Set a font and do some styling
```html
data:text/html,
<body contenteditable style="line-height:1.5;font-size:30px;font-family:Roboto">
```

#### 2. Draw
```html
data:text/html,<canvas id="v"><script>d=document,d.body.style.margin=0,f=0,c=v.getContext("2d"),v.width=innerWidth,v.height=innerHeight,c.lineWidth=2,x=e=>e.clientX||e.touches[0].clientX,y=e=>e.clientY||e.touches[0].clientY,d.onmousedown=d.ontouchstart=e=>{f=1,e.preventDefault(),c.moveTo(x(e),y(e)),c.beginPath()},d.onmousemove=d.ontouchmove=e=>{f&&(c.lineTo(x(e),y(e)),c.stroke())},d.onmouseup=d.ontouchend=e=>f=0</script>

```
#### 3. Presentations
```html
data:text/html,<style>@page{size: 6in 8in landscape;}</style><body><script>d=document;for(i=0;i<50;i++)d.body.innerHTML+='<div style="position:relative;width:90%;padding-top:60%;margin:5%;border:1px solid silver;page-break-after:always;"><div contenteditable style="outline:none;position:absolute;right:10%;bottom:10%;left:10%;top:10%;font-size:5vmin;"></div></div>';d.querySelectorAll("div>div").forEach(e=>e.onkeydown=e=>{n=e.ctrlKey&&e.altKey&&e.keyCode-49,x=["formatBlock","formatBlock","justifyLeft","justifyCenter","justifyRight","outdent","indent","insertUnorderedList"][n],y=["<h1>","<div>"][n],x&&document.execCommand(x,!1,y)})</script>

```
