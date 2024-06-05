# codeAlpha_Calculator
#Task-2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>#Task-2 || Calculator </title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <input id="inputBox" type="text" placeholder="0" >
    
    <div>
    <button class="operator">AC</button>
    <button class="operator">DEL</button>
    <button class="operator">%</button>
    <button class="operator">/</button>
    </div>
    <div>
        <button>7</button>
        <button>8</button>
        <button>9</button>
        <button class="operator">*</button>
        </div>
        <div>
            <button>4</button>
            <button>5</button>
            <button>6</button>
            <button class="operator">-</button>
            </div>
            <div>
                <button>1</button>
                <button>2</button>
                <button>3</button>
                <button class="operator">+</button>
                </div>
                <div>
                    <button>00</button>
                    <button>0</button>
                    <button>.</button>
                    <button class="answer">=</button>
                    </div>
                    </div>
                    <script src="script.js"></script>
</body>
</html>

style.css

@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Poppins", sans-serif;
}
body{
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: linear-gradient(45deg,#0a0a0a,#3a4452);
}
.container{
    border: 1px solid #717377;
    padding: 5px;
    border-radius: 16px;
    background: transparent;
    box-shadow: 0px 3px 15px rgba(113,115,119,0.5);
}
input{
    width: 320px;
    border: none;
    padding: 24px;
    margin: 10px;
    background: transparent;
    box-shadow: 0px 3px 15px rgba(84,84,84,0.1);
    font-size: 40px;
    text-align: right;
    cursor: pointer;
    background-color: white;

}
input::placeholder{
    color: black;
}
button{
    border: none;
    width: 65px;
    margin: 10px;
    height:60px;
    border-radius: 50%;
    background: transparent;
    color: white;
    font-size: 20px;
    box-shadow: -8px -8px 15px rgba(255,255,255,0.1);
    cursor: pointer;
    
}
.answer{
    background-color: orange;

}
.operator{
    color: green;
}
script.js
let display=document.getElementById("inputBox");
let buttons=document.querySelectorAll("button");
let buttonsArray=Array.from(buttons);
let string='';

buttons.forEach(btn=>{
    btn.addEventListener('click',(e)=>{
        if(e.target.innerHTML=='DEL'){
            string=string.substring(0,string.length-1);
            display.value=string;
       }
       else if(e.target.innerHTML=='AC'){
        string='';
        display.value=string;
       }
       else if(e.target.innerHTML=='='){
        string=eval(string);
        display.value=string;
       }
       else{
        string+=e.target.innerHTML;
        display.value=string;
       }
    })
})
