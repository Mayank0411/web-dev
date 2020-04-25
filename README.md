<!doctype html>
<html>
	<head>
		<title>no. count</title>
		<meta name="mynogame" content="delta"/>
		<style type="text/css">
		body{
			font-family:verdana,serif,sans-serif;
			background-color: #696969    ;
			}
		h1	{
			margin:10px auto auto auto;
			text-align:center;
			font-size:430%;
			text-transform:uppercase;
			text-color:#ADFF2F ;
			text-decoration:underline;
			text-shadow: 7px 2px 3px  #FF00FF ;
		}
		.par  {
			text-align:center;
			font-family:arial;
			color: #ADFF2F;
			text-transform:uppercase;
			font-size:150%;
			font-weight:bold;
			text-shadow: 2px 2px 3px #000000;
			
			
		}
		#pad {
			margin:auto 32% auto 38%;
			border:4px solid #8B008B  ;
			padding:1.6%;
			width:21.4%;
			height:28%;
			background-color: #9FAFDF   ;
			float:left;
			display:inline;
			
			}
		.button{
			border:3px solid  #000080 ;
			width:60px;
			height:60px;
			margin:3%;
			background-color:black ;
			color:white;
			font-size:28px;
			
		}
		.button:hover{
					border-color:black;
					font-size:30px;
					color:red;
			} 
		.button:active{
				border:8px solid  #000080 ;
		
		
			}
		#New {
				font-size:300%;
				font-weight:bold;
				margin-right:11%;
				color:  #000080 ;
				float:right;
				background-color:#B0E0E6 ;
				border:2px solid blue;
				}
		#stopwatch{
					font-size:300%;
					font-weight:bold;
					color: #000080 ;
					margin-left:14%;
					float:left;
					border:2px solid blue;
					background-color: #B0E0E6;
				}
		#New:hover{
					border:1px solid red;
					color:red;
		
		}
		#yourscore{
				margin:auto 45% auto 30%;
				font-size:120%;
				color: #000080 ;
				float:left;
				text-shadow: 2px 2px 3px #000000;
				}
		.bs{
				margin:auto 45% auto 30%;
				float:right;
				width=200px;
				height:50px;
				text-align:center;
				color:#000080;
				font-weight:bold;
				font-size:120%;
				background-color:#B0E0E6;
				border:2px solid blue;
				}
		
		.bs:hover{
					border:1px solid red;
					color:red;
					}
		#demo{
				margin:auto 42% auto 30%;
				float:right;
				font-size:120%;
				color:red;
				text-shadow: 2px 2px 3px #000000;
		
			}
		
		
		
		</style>
	</head>
<body>

<h1>number game</h1>
<p class="par">type no. as soon as possible in ascending order</p>
	<button id="New">NEW GAME</button>
	<span id="stopwatch"></span>
	<p><div id="pad">
		<button class="button" id="11">11</buttom>
		<button class="button" id="3">3</buttom>
		<button class="button" id="10">10</buttom>
		<button class="button" id="18">18</buttom>
		<button class="button" id="5">5</buttom>
		<button class="button" id="13">13</buttom>
		<button class="button" id="7">7</buttom>
		<button class="button" id="14">14</buttom>
		<button class="button" id="2">2</buttom>
		<button class="button" id="16">16</buttom>
		<button class="button" id="4">4</buttom>
		<button class="button" id="17">17</buttom>
		<button class="button" id="1">1</buttom>
		<button class="button" id="8">8</buttom>
		<button class="button" id="12">12</buttom>
		<button class="button" id="9">9</buttom>
		<button class="button" id="6">6</buttom>
		<button class="button" id="19">19</buttom>
		<button class="button" id="15">15</buttom>
		<button class="button" id="20">20</buttom>
		</div>
		</p>
		</br></br></br></br>
		<p id="yourscore"></p></br>
		<button class="bs" onclick="myFunction()">bestscore</button>
		<p id="demo"></p>




		<script>
		var click=0;
		document.getElementById("New").onclick=function() {Newgame()};
		function Newgame(){
		click=0;
		stopwatch.reset();
		document.getElementById("1").innerHTML=1;
		document.getElementById("2").innerHTML=2;
		document.getElementById("3").innerHTML=3;
		document.getElementById("4").innerHTML=4;
		document.getElementById("5").innerHTML=5;
		document.getElementById("6").innerHTML=6;
		document.getElementById("7").innerHTML=7;
		document.getElementById("8").innerHTML=8;
		document.getElementById("9").innerHTML=9;
		document.getElementById("10").innerHTML=10;
		document.getElementById("11").innerHTML=11;
		document.getElementById("12").innerHTML=12;
		document.getElementById("13").innerHTML=13;
		document.getElementById("14").innerHTML=14;
		document.getElementById("15").innerHTML=15;
		document.getElementById("16").innerHTML=16;
		document.getElementById("17").innerHTML=17;
		document.getElementById("18").innerHTML=18;
		document.getElementById("19").innerHTML=19;
		document.getElementById("20").innerHTML=20;
		
		
		
		
		
		}
		
			
			
		
			class Stopwatch {
    constructor(display, results) {
        this.running = false;
        this.display = display;
        this.results = results;
        this.reset();
        this.print(this.times);
    }
    
    reset() {
        this.times = [ 0, 0, 0 ];
    }
    
   start() {
        if (!this.time) this.time = performance.now();
        if (!this.running) {
            this.running = true;
            requestAnimationFrame(this.step.bind(this));
        }
    }
    
    stop() {
      if(document.getElementById("20").innerHTML==40){
        this.running = false;
        this.time = null;
    }}
    
    step(timestamp) {
        if (!this.running) return;
        this.calculate(timestamp);
        this.time = timestamp;
        this.print();
        requestAnimationFrame(this.step.bind(this));
    }
    
    calculate(timestamp) {
        var diff = timestamp - this.time;
        // Hundredths of a second are 100 ms
        this.times[2] += diff / 10;
        // Seconds are 100 hundredths of a second
        if (this.times[2] >= 100) {
            this.times[1] += 1;
            this.times[2] -= 100;
        }
        // Minutes are 60 seconds
        if (this.times[1] >= 60) {
            this.times[0] += 1;
            this.times[1] -= 60;
        }
    }
    
    print() {
        this.display.innerText = this.format(this.times);
    }
    
    format(times) {
        return `\
${pad0(times[0], 2)}:\
${pad0(times[1], 2)}:\
${pad0(Math.floor(times[2]), 2)}`;
    }
}

function pad0(value, count) {
    var result = value.toString();
    for (; result.length < count; --count)
        result = '0' + result;
    return result;
}

function clearChildren(node) {
    while (node.lastChild)
        node.removeChild(node.lastChild);
}

let stopwatch = new Stopwatch(
    document.querySelector('#stopwatch'),
    document.querySelector('#results'));			
		
		
		
			document.getElementById("1").onclick = function() {myFunction1()};
			function myFunction1() {
                 if(document.getElementById("1").innerHTML==click+1){
			stopwatch.start();
                  click=click+1;
			if(document.getElementById("1").innerHTML==01){
				document.getElementById("1").innerHTML = 21;
			}
			else{ document.getElementById("1").innerHTML = 0}
			}
                     else{alert("wrong click");}
                       }
			
			
			
			
			document.getElementById("2").onclick = function() {myFunction2()};
			function myFunction2() {
                        if(document.getElementById("2").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("2").innerHTML==02){
				document.getElementById("2").innerHTML = 22;
			}
			else{ document.getElementById("2").innerHTML = 0}
			}
                        else{alert("wrong click");}
                         }
			
			
			
			document.getElementById("3").onclick = function() {myFunction3()};
			function myFunction3() {
                       if(document.getElementById("3").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("3").innerHTML==03){
				document.getElementById("3").innerHTML = 23;
			}
			else{ document.getElementById("3").innerHTML = 0}
			}
			else{alert("wrong click");}
                          }
			
			
			document.getElementById("4").onclick = function() {myFunction4()};
			function myFunction4() {
                        if(document.getElementById("4").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("4").innerHTML==04){
				document.getElementById("4").innerHTML = 24;
			}
			else{ document.getElementById("4").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			
			
			
			document.getElementById("5").onclick = function() {myFunction5()};
			function myFunction5() {
                       if(document.getElementById("5").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("5").innerHTML==05){
				document.getElementById("5").innerHTML = 25;
			}
			else{ document.getElementById("5").innerHTML = 0}
			}
			else{alert("wrong click");}
                         }
			
			
			document.getElementById("6").onclick = function() {myFunction6()};
			function myFunction6() {
                         if(document.getElementById("6").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("6").innerHTML==06){
				document.getElementById("6").innerHTML = 26;
			}
			else{ document.getElementById("6").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			
			
			document.getElementById("7").onclick = function() {myFunction7()};
			function myFunction7() {
                          if(document.getElementById("7").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("7").innerHTML==07){
				document.getElementById("7").innerHTML = 27;
			}
			else{ document.getElementById("7").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			
			
			document.getElementById("8").onclick = function() {myFunction8()};
			function myFunction8() {
                        if(document.getElementById("8").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("8").innerHTML==08){
				document.getElementById("8").innerHTML = 28;
			}
			else{ document.getElementById("8").innerHTML = 0}
			}
                        else{alert("wrong click");}
                        }
			
			
			
			document.getElementById("9").onclick = function() {myFunction9()};
			function myFunction9() {
                        if(document.getElementById("9").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("9").innerHTML==09){
				document.getElementById("9").innerHTML = 29;
			}
			else{ document.getElementById("9").innerHTML = 0}
			}
			else{alert("wrong click");}
			}
			
			document.getElementById("10").onclick = function() {myFunction10()};
			function myFunction10() {
                        if(document.getElementById("10").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("10").innerHTML==10){
				document.getElementById("10").innerHTML = 30;
			}
			else{ document.getElementById("10").innerHTML = 0}
			}
			else{alert("wrong click");}
			}
			document.getElementById("11").onclick = function() {myFunction11()};
			function myFunction11() {
                         if(document.getElementById("11").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("11").innerHTML==11){
				document.getElementById("11").innerHTML = 31;
			}
			else{ document.getElementById("11").innerHTML = 0}
			}
			else{alert("wrong click");}
                       }
			
			document.getElementById("12").onclick = function() {myFunction12()};
			function myFunction12() {
                       if(document.getElementById("12").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("12").innerHTML==12){
				document.getElementById("12").innerHTML = 32;
			}
			else{ document.getElementById("12").innerHTML = 0}
			}
			else{alert("wrong click");}
			}
			
			document.getElementById("13").onclick = function() {myFunction13()};
			function myFunction13() {
                        if(document.getElementById("13").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("13").innerHTML==13){
				document.getElementById("13").innerHTML = 33;
			}
			else{ document.getElementById("13").innerHTML = 0}
			}
			else{alert("wrong click");}
			}
			document.getElementById("14").onclick = function() {myFunction14()};
			function myFunction14() {
                        if(document.getElementById("14").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("14").innerHTML==14){
				document.getElementById("14").innerHTML = 34;
			}
			else{ document.getElementById("14").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			document.getElementById("15").onclick = function() {myFunction15()};
			function myFunction15() {
                        if(document.getElementById("15").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("15").innerHTML==15){
				document.getElementById("15").innerHTML = 35;
			}
			else{ document.getElementById("15").innerHTML = 0}
			}
			else{alert("wrong click");}
                         }
			
			document.getElementById("16").onclick = function() {myFunction16()};
			function myFunction16() {
                        if(document.getElementById("16").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("16").innerHTML==16){
				document.getElementById("16").innerHTML = 36;
			}
			else{ document.getElementById("16").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			
			document.getElementById("17").onclick = function() {myFunction17()};
			function myFunction17() {
                         if(document.getElementById("17").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("17").innerHTML==17){
				document.getElementById("17").innerHTML = 37;
			}
			else{ document.getElementById("17").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			document.getElementById("18").onclick = function() {myFunction18()};
			function myFunction18() {
                        if(document.getElementById("18").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("18").innerHTML==18){
				document.getElementById("18").innerHTML = 38;
			}
			else{ document.getElementById("18").innerHTML = 0}
			}
			else{alert("wrong click");}
                        }
			
			document.getElementById("19").onclick = function() {myFunction19()};
			function myFunction19() {
                        if(document.getElementById("19").innerHTML==click+1){
                       click=click+1;
			if(document.getElementById("19").innerHTML==19){
				document.getElementById("19").innerHTML = 39;
			}
			else{ document.getElementById("19").innerHTML = 0}
			}
                        else{alert("wrong click");}
                        }
			
			
			document.getElementById("20").onclick = function() {myFunction20()};
			function myFunction20() {
                        if(document.getElementById("20").innerHTML==click+1){
                        stopwatch.stop();
                        click=click+1;
			if(document.getElementById("20").innerHTML==20){
				document.getElementById("20").innerHTML = 40;
			}
			else{
			var num=document.getElementById("stopwatch").innerHTML;
			var string=num.toString();
			topscores.push(string);
			document.getElementById("yourscore").innerHTML="<h2>your last score was: "+document.getElementById("stopwatch").innerHTML+" time</h2>";
			
			}
			}
			else{alert("wrong click");}
            }
			
						
						var topscores = [];
			

			function myFunction() {
				topscores.sort();
				var text, fLen, i;
				fLen = topscores.length;

				text = "<ul>";
				for (i = 0; i < fLen; i++) {
				  text += "<li>" + topscores[i] + "</li>";
				}
				text += "</ul>";
			    document.getElementById("demo").innerHTML = "<h3>best scores are:<h3>"+topscores;
				}
			
			
			
			
			
		</script>
	
</body>
</html>
