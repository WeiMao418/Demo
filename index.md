
<!doctype html>
<html lang="zh_tw">
<head>
<meta charset="utf-8">
<script>
var hit=0;
function over(obj)
{
   document.getElementById("ans");   
}
function mout(obj)
{
   document.getElementById("ans");   
}

document.addEventListener("mouseup",mu,false);
    
function mu(e)
{
   hit=0;
   document.getElementById("ans");   
}
document.addEventListener("mousemove",mv,false);
function mv(e)
{
    if (hit==0) return;
    IE = document.all ? true : false;
    e=window.event || e;
     var x,y;
    if (IE)
    {
        y=e.clientY+document.body.scrollTop ;
        x=e.clientX+document.body.scrollLeft;
    }
    else
    {
        y=e.pageY;
        x=e.pageX;
    }
    document.getElementById("xxx").style.left=x+"px";
    document.getElementById("xxx").style.top=y+"px";
    document.getElementById("ans");   
}
document.addEventListener("mousedown",md,false);
function md(e)
{
    e=window.event || e;
     IE = document.all ? true : false;
     var x,y;
    if (IE)
    {
        y=e.clientY+document.body.scrollTop ;
        x=e.clientX+document.body.scrollLeft;
    }
    else
    {
        y=e.pageY;
        x=e.pageX;
    }
    var MX,MY,MW,MH;
    MX=parseInt(document.getElementById("xxx").style.left);
    MY=parseInt(document.getElementById("xxx").style.top);
    MW=parseInt(document.getElementById("yyy").width);
    MH=parseInt(document.getElementById("yyy").height);
    if (x>MX  && y> MY && x<MX+MW && y< MY+MH)
        hit=1;
     document.getElementById("ans");   
}
function up()

{
    var aa=document.getElementById("xxx")
    var x=parseInt(aa.style.left);
    var y=parseInt(aa.style.top);
    y=y-10;
    if(y<0)y=300;
    aa.style.top=y+"px";
}
function down()
{
    var aa=document.getElementById("xxx")
    var x=parseInt(aa.style.left);
    var y=parseInt(aa.style.top);
    y=y+10;
    if(y>300)y=0;
    aa.style.top=y+"px";
}
function left()
{
    var aa=document.getElementById("xxx")
    var x=parseInt(aa.style.left);
    var y=parseInt(aa.style.top);
   x=x-10;
    if(x<0)x=500;
    aa.style.left=x+"px";
}
function right()
{
    var aa=document.getElementById("xxx")
    var x=parseInt(aa.style.left);
    var y=parseInt(aa.style.top);
    x=x+10;
    if(x>500)x=0;
    aa.style.left=x+"px";
}
</script>
<title>WEIWEIMAO</title>
</head>
<body>
<article id="xxx" style="position:absolute; top:175px; left:34px;" onmouseover="over(this)">
<img id="yyy" src="https://static.styletc.com/images/cover/15/106115/md-812c1851f10ff97efba23c18d1946595.jpg" width="300" onmouseout="mout(this)">
<div id="ans"></div>
</article>

</body>
</html>


