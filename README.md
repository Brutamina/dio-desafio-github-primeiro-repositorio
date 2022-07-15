# dio-desafio-github-primeiro-repositorio
Desafio de projeto sobre git/github 
JOGO DO DINOSSAURO COM HTML, CSS E JAVASCRIPT 

HTML

<!DOCTYPE html>
<html lang="en" onclick="pular()">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./style.css">
    <title>Jogo do Dinossauro</title>
</head>
<body>
    <div id="game">
        <div id="personagem"></div>
        <div id="quadrado"></div>
    
</body>

<script src="./script.js"></script>
</html>


Css

*{
    margin: 0;
    padding: 0;
}
#game {
    width: 500px;
    height: 200px;
    border: 1px solid black; 
}
#personagem{
    width: 20px;
    height: 50px;
    background-color: red;
    position: relative;
    top: 150px;
}
.animar {
    animation: personagem 500ms  infinite;




}

@keyframes personagem {
    0%{top: 150px;}
    30%{top: 100px;}
    70%{top: 100px;}
    100%{top: 150px;}
    
}
#quadrado {
    width: 20px;
    height: 20px;
    background-color: blue;
    position: relative;
    top: 130px;
    left: 480px;
    animation: quadrado 1s infinite linear;
}
@keyframes quadrado {
    0%{left: 480px;}
    100%{left: -40px;}
    
}


javascript 

let personagem = document.querySelector("#personagem")
let quadrado =document.querySelector("#quadrado")

function pular(){
    if(personagem.classList !="animar"){
        personagem.classList.add("animar")
}
 

setTimeout(function(){
personagem.classList.remove("animar")
}, 500 ) 
}

var testarcolisao = setInterval( function(){

     var topoPersonagem =parseInt(
        window.getComputedStyle(personagem).getPropertyvalue("top")
     )
     var esquerdaquadrado =parseInt(
        window.getComputedStyle(quadrado).getPropertyvalue("left")
     )
     if (esquerdaquadrado <20 && esquerdaquadrado >0  && topopersonagem >= 130) {
        quadrado.style.animation = "none"
        quadrado.style.animation ="none"
        alert("voce perdeu!")
     }


     
}, 10)


