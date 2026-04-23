<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Love You ❤️</title>

<style>
body{
    margin:0;
    background:#F5E8DC;
    font-family: Arial;
    text-align:center;
    overflow:hidden;
}

/* Texto */
.texto{
    position:absolute;
    top:10%;
    width:100%;
    color:#5C4033;
    font-size:18px;
}

/* Corazones flotando */
.corazon{
    position:absolute;
    color:red;
    animation: subir linear infinite;
}

@keyframes subir{
    0%{transform:translateY(100vh) scale(0.5);}
    100%{transform:translateY(-10vh) scale(1.2);}
}

/* Árbol */
.arbol{
    position:absolute;
    bottom:0;
    left:50%;
    transform:translateX(-50%);
    width:20px;
    height:150px;
    background:#5C4033;
}

.copa{
    position:absolute;
    bottom:150px;
    left:50%;
    transform:translateX(-50%);
    width:200px;
    height:200px;
    background:pink;
    border-radius:50%;
    box-shadow:0 0 50px pink;
}

/* contador */
#contador{
    margin-top:20px;
    font-weight:bold;
}
</style>
</head>

<body>

<div class="texto">
    <p><b>Para el amor de mi vida ❤️</b></p>
    <p>
    Si pudiera elegir un lugar seguro, sería a tu lado.<br>
    Cuanto más tiempo estoy contigo más te amo.
    </p>

    <div id="contador"></div>
</div>

<div class="arbol"></div>
<div class="copa"></div>

<script>
// CONTADOR
const inicio = new Date("2018-11-24T00:00:00");

function actualizar(){
    const ahora = new Date();
    const d = ahora - inicio;

    const dias = Math.floor(d/(1000*60*60*24));
    const horas = Math.floor((d/(1000*60*60))%24);
    const min = Math.floor((d/(1000*60))%60);
    const seg = Math.floor((d/1000)%60);

    document.getElementById("contador").innerHTML =
    `Mi amor por ti comenzó hace...<br>
    ${dias} días ${horas} horas ${min} min ${seg} seg ❤️`;
}
setInterval(actualizar,1000);

// CORAZONES
function crearCorazon(){
    const c = document.createElement("div");
    c.className="corazon";
    c.innerHTML="❤️";
    c.style.left=Math.random()*100+"vw";
    c.style.animationDuration=(3+Math.random()*5)+"s";
    document.body.appendChild(c);

    setTimeout(()=>c.remove(),8000);
}
setInterval(crearCorazon,300);
</script>

</body>
</html>
