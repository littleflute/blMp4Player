 <a href="https://github.com/littleflute/blMp4Player/edit/master/README.md">v0.0.4</a>
 
<div id="blID_Mp4Player" style="border:1px red solid;width:50px;height:550px;"></div> 

<button onclick="p.showMyCode2Div(this,'code');">+</button>

<div id="code" style="top:80px;left:10px;width:220px;border:1px blue solid;"></div>
<script>
//<
function blMp4Player() { 
	this.ui				= null;
	this.v				= "v0.2.1";
	this.src			= "https://littleflute.github.io/Stevie-Ray-Vaughan/STEVIE_RAY_VAUGHAN/STEVIE_RAY_VAUGHAN 00_04_18-00_09_52.mp4";
    this.onBtnTest		= function(o)
    {
    	var id = "x" + o.parentElement.id;
      	var x = document.getElementById(id);
    	if(x.style.display == "none")
    	{
    		x.style.display = "block";
        	o.innerHTML = "-";
       	 o.style.color = "red";
    	}
    	else
    	{
    		x.style.display = "none";
        	o.innerHTML = "+";
        	o.style.color = "green";
    	}
    };
    this.bShowCode		= false; 
    this.showMyCode2Div		= function (btn,divId)
    {
    	var x;
		var h = document.getElementById(divId);
		if(!h) return; 

		this.bShowCode = !this.bShowCode;
		btn.innerHTML = this.bShowCode?"-":"+";
		if(!this.bShowCode) {h.innerHTML = ""; return;}

        var nID = 0;
		for(x in this)
		{
        	nID++;
            
			var d = document.createElement("div");
			d.id = nID;
            d.onFun = this.onBtnTest;
            d.innerHTML = x;
            var bt= "<button onclick='this.parentElement.onFun(this)'>";
            bt += "+</button>";
			d.innerHTML += bt;
            d.style.border = "solid 1px blue";
			d.style.color = "red";
			h.appendChild(d); 
            
			var v = document.createElement("div");
            v.id = "x" + nID;
			v.innerHTML = this[x];
			v.style.border = "solid 1px green";
			v.style.color = "black";
            v.style.display = "none";
			d.appendChild(v); 
		} 
 
    }
	this.createVideo	= function ()
	{
		var d = document.createElement("div");
		d.style.border = "1px blue solid";
		var ui = this.getUI();
 		ui.appendChild(d);
		var s = "";
		s += "<video id='bl_Video' width='320px' height='240px' controls>";
		s += "<source src='";
        s += this.src;
        s += "' type='video/mp4'>";
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
		me.innerHTML = this.v; 
		o.appendChild(me);
		this.createVideo();
	};

	this.play		= function ()
	{
		if(this.v == null) this.createVideo();
		this.v.play();
	};

	this.stop		= function ()
	{
		if(this.v == null) this.createVideo();
		this.v.stop();
	};
}   
//-->
var p = new blMp4Player();
p.showMe();

//-->

</script>  
