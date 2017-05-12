[v0.0.2](https://github.com/littleflute/blMp4Player/edit/master/README.md)


<div id="blID_Mp4Player" style="border:1px blue solid;width:5px;height:550px;"></div> 
 
<script>
//<
function blMp4Player() { 
	this.ui				= null;
	this.v				= null;
	this.vSrc			= "";

	this.createVideo	= function ()
	{
		var d = document.createElement("div");
		d.style.border = "1px blue solid";
		var ui = this.getUI();
 		ui.appendChild(d);
		var s = "";
		s += "<video id='bl_Video' width='320px' height='240px' controls>";
		s += "<source src='en_7_8_ex.mp4' type='video/mp4'>";
		s += "Your browser does not support HTML5 video.";
		s += "</video>"; 

		d.innerHTML = s;

	};
	this.getUI		= function ()
	{
		if(this.ui == null)
		{
			var el				= document.createElement("div");
			el.style.position	= "absolute";
			el.style.border		= "1px green solid";
			el.style.width		= "330px";
			el.style.left		= "300px";
			this.ui			= el;
		}
		return this.ui;
	};
	this.showMe		= function ()
	{  
		var o = document.getElementById("blID_Mp4Player"); 
		var me = this.getUI();
		me.innerHTML = "mp4: v0.1.8"; 
		o.appendChild(me);
		this.createVideo();
	};

	this.play		= function ()
	{
		if(this.v == null) this.createVideo();
		this.v.play();
	};
}   
//-->
var p = new blMp4Player();
p.showMe();

//-->

</script> 





~~~html
<!DOCTYPE html>	  
<html>  
<body>  
<div id="blID_Mp4Player" style="border:1px blue solid;width:50px;height:50px;"></div> 
 
<script>
//<
function blMp4Player() { 
	this.ui				= null;
	this.v				= null;
	this.vSrc			= "";

	this.createVideo	= function ()
	{
		var d = document.createElement("div");
		d.style.border = "1px blue solid";
		var ui = this.getUI();
 		ui.appendChild(d);
		var s = "";
		s += "<video id='bl_Video' width='320px' height='240px' controls>";
		s += "<source src='en_7_8_ex.mp4' type='video/mp4'>";
		s += "Your browser does not support HTML5 video.";
		s += "</video>"; 

		d.innerHTML = s;

	};
	this.getUI		= function ()
	{
		if(this.ui == null)
		{
			var el				= document.createElement("div");
			el.style.position	= "absolute";
			el.style.border		= "1px green solid";
			el.style.width		= "330px";
			el.style.left		= "300px";
			this.ui			= el;
		}
		return this.ui;
	};
	this.showMe		= function ()
	{  
		var o = document.getElementById("blID_Mp4Player"); 
		var me = this.getUI();
		me.innerHTML = "mp4: v0.1.8"; 
		o.appendChild(me);
		this.createVideo();
	};

	this.play		= function ()
	{
		if(this.v == null) this.createVideo();
		this.v.play();
	};
}   
//-->
var p = new blMp4Player();
p.showMe();

//-->

</script> 
</body> 
~~~
