

<html>
<head>
<title>Shulman games</title>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>

<script type="text/javascript" src="https://static.codehs.com/gulp/3f84459863ed2daae2bf34ef9692d3246a944219/chs-js-lib/chs.js"></script>


<style>
canvas {
    border: 1px solid black;
    display: inline-block;
    vertical-align: top;
}

pre {
    border: 1px solid black;
    display: inline-block;
    width: 400px;
    height: 500px;
    background-color: #F5F5F5;
}
    
    body{
        
        background-color: cornflowerblue;
        
        
    }
    
</style>

</head>

<body>
    
    
    
<h1 style="text-align: center; color: cyan; font-family: impact; font-size: 50px;">Collect all the coins</h1>
<h2 style="text-align: center; color: cyan; font-family: impact; font-size: 30px;">instructions:</h2>
<h3 style="text-align: center; color: cyan; font-family: impact; font-size: 20px;">-You have 10 seconds before game over</h3>
<h4 style="text-align: center; color: cyan; font-family: impact; font-size: 20px;">-Use keypad to move the Jew</h4>



<div align="center">
<canvas
width="400"
height="500"
class="codehs-editor-canvas"></canvas>
</div>


<script>
window.onload = function() {

    
////////////////////darkness///////////////////////////
var dark = new Rectangle(getWidth(),getHeight());

///////////////////jews///////////////////////
var yid = new WebImage("http://www.jewishmag.com/171mag/jewish_learning/title.gif");

//////////////////egyptions//////////////////////
var egyption = new WebImage("http://www.historyforkids.net/images/egypt_king.gif");
var egyption2 = new WebImage("http://www.historyforkids.net/images/egypt_king.gif");
var egyption3 = new WebImage("http://www.historyforkids.net/images/egypt_king.gif");

/////////////////lights////////////////////////
var light = new Circle(60);
var light2 = new Circle(60);
var light3 = new Circle(60);
var light4 = new Circle(60);
var light5 = new Circle(60);
var light6 = new Circle(60);

////////////////text///////////////////////////

var txt = new Text("Why can the Jews see but we cant!?", "18pt Arial");


var gold = new Circle(20);
var gold1 = new Circle(20);
var gold2 = new Circle(20);
var gold3 = new Circle(20);
var gold4 = new Circle(20);

var txtMoney = new Text("$");
var txtMoney1 = new Text("$");
var txtMoney2 = new Text("$");
var txtMoney3 = new Text("$");
var txtMoney4 = new Text("$");
var score = new Text("$10");
var scoreAdd = new Text(score + "10");
//var txtScore = new Text("$" + moneyScore );



function background(){
 
 dark.setColor(Color.black);
 add(dark);
    
}

function person(){
    
    yid.setSize(60,70);
    yid.setPosition(40,40);
    add(yid);
    
    
    egyption.setSize(70,90);
    egyption.setPosition(220,245);
    add(egyption);
    
    egyption2.setSize(70,90);
    egyption2.setPosition(40,150);
    add(egyption2);
    
    egyption3.setSize(70,90);
    egyption3.setPosition(170,350);
    add(egyption3);
    
}

function brightness(){
    
    light.setPosition(60,70);
    light.setColor(Color.yellow);
    add(light);
    
    
    //light4.setPosition(250,300);
    //light4.setColor(Color.yellow);
    //add(light4);
    
    light5.setPosition(70,200);
    light5.setColor(Color.yellow);
    //add(light5);
    
    light6.setPosition(200,400);
    light6.setColor(Color.yellow);
    //add(light6);
    
    
    
}

function removeLight(){
    
    //remove(light4);
    //remove(light5);
    //remove(light6);
    

}


function moveYid1(e){
    
    if (e.keyCode == Keyboard.LEFT) {
        light.move(-20,0);
    }
    
    if (e.keyCode == Keyboard.LEFT) {
        yid.move(-20,0);
    }
    
    if (e.keyCode == Keyboard.RIGHT) {
        light.move(20,0);
    }
    
    if (e.keyCode == Keyboard.RIGHT) {
        yid.move(20,0);
    }
    
    if (e.keyCode == Keyboard.DOWN) {
        light.move(0,20);
    }
    
    if (e.keyCode == Keyboard.DOWN) {
        yid.move(0,20);
    }
    
    if (e.keyCode == Keyboard.UP) {
        light.move(0,-20);
    }
    
    if (e.keyCode == Keyboard.UP) {
        yid.move(0,-20);
    }
    
    
}

function makeGold(){
    
    gold.setPosition(270,100);
    gold.setColor(Color.green);
    add(gold);
    
    txtMoney.setPosition(263,108);
    txtMoney.setColor(Color.white);
    add(txtMoney);
    
    gold1.setPosition(200,200);
    gold1.setColor(Color.green);
    add(gold1);
    
    txtMoney1.setPosition(193,206);
    txtMoney1.setColor(Color.white);
    add(txtMoney1);
    
    gold2.setPosition(300,400);
    gold2.setColor(Color.green);
    add(gold2);
    
    txtMoney2.setPosition(293,407);
    txtMoney2.setColor(Color.white);
    add(txtMoney2);
    
    gold3.setPosition(80,360);
    gold3.setColor(Color.green);
    add(gold3);
    
    txtMoney3.setPosition(73,370);
    txtMoney3.setColor(Color.white);
    add(txtMoney3);
    
    gold4.setPosition(40,440);
    gold4.setColor(Color.green);
    add(gold4);
    
    txtMoney4.setPosition(33,445);
    txtMoney4.setColor(Color.white);
    add(txtMoney4);
    
    
}

function checkCirclesCombine(){
    if(yid.getX()==240 && yid.getY()==60){
        //moneyScore += 10;
        //txtScore.setPosition(280,40);
        //txtScore.setColor(Color.white);
        //add(txtScore);
        //println(txtScore);
        score.setPosition(280,40);
        score.setColor(Color.white);
        add(score);
        remove(gold);
        remove(txtMoney);
    }
    
    if(yid.getX()==60 && yid.getY()==320){
        //moneyScore += 10;
        //txtScore.setPosition(280,40);
        //txtScore.setColor(Color.white);
        //add(txtScore);
        //println(txtScore);
        remove(gold3);
        remove(txtMoney3);
    }
    
    if(yid.getX()==280 && yid.getY()==360){
        //moneyScore += 10;
        //txtScore.setPosition(280,40);
        //txtScore.setColor(Color.white);
        //add(txtScore);
        //println(txtScore);
        remove(gold2);
        remove(txtMoney2);
    }
    
    
    if(yid.getX()==20 && yid.getY()==400){
        //moneyScore += 10;
        //txtScore.setPosition(280,40);
        //txtScore.setColor(Color.white);
        //add(txtScore);
        //println(txtScore);
        remove(gold4);
        remove(txtMoney4);
    }
    
    
        if(yid.getX()==180 && yid.getY()==160){
        //moneyScore += 10;
        //txtScore.setPosition(280,40);
        //txtScore.setColor(Color.white);
        //add(txtScore);
        //println(txtScore);
        remove(gold1);
        remove(txtMoney1);
        
        
    }else{
         print("yidx="+yid.getX()+"yidy="+yid.getY()+  "   gold1   x=" + gold1.getX() + "y =" + gold1.getY());
        println(" no meeting");
    }
    
    
    
}
    
    
    
    var gameOver = new Text("Game Over!!","60pt Impact");
    var gameOver2 = new Text("Press refresh to restart game","20pt Impact");


    function finish()
    {
    removeAll();
    gameOver.setPosition(0,200);
    gameOver.setColor(Color.green);
    add(gameOver);
        
    gameOver2.setPosition(0,250);
    gameOver2.setColor(Color.green);
    add(gameOver2);    
    
    }


function start(){
    
    background();
    brightness();
    person();
    mouseClickMethod(removeLight);
    keyDownMethod(moveYid1);
    makeGold();
    setTimer(checkCirclesCombine,20);
    setTimer(finish,10000);
    
    
}



    if (typeof start === 'function') {
        start();
    }
};
</script>

</body>
</html>
