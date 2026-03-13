<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Intro Yin Yang</title>

<style>
body{
    margin:0;
    font-family:Arial, Helvetica, sans-serif;
    background:#111;
    color:white;
    overflow:hidden;
}

/* Tela da intro */
#intro{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background:black;
    display:flex;
    align-items:center;
    justify-content:center;
    flex-direction:column;
    z-index:10;
}

/* Símbolo Yin Yang */
.yinyang{
    width:150px;
    height:150px;
    border-radius:50%;
    background:linear-gradient(white 50%, black 50%);
    position:relative;
    animation:spin 3s linear infinite;
}

.yinyang::before,
.yinyang::after{
    content:"";
    position:absolute;
    left:50%;
    transform:translateX(-50%);
    width:75px;
    height:75px;
    border-radius:50%;
}

.yinyang::before{
    top:0;
    background:black;
    box-shadow:0 0 0 20px white inset;
}

.yinyang::after{
    bottom:0;
    background:white;
    box-shadow:0 0 0 20px black inset;
}

/* Animação de rotação */
@keyframes spin{
    from{ transform:rotate(0deg); }
    to{ transform:rotate(360deg); }
}

/* Conteúdo principal */
#content{
    display:none;
    height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:40px;
}
</style>
</head>

<body>

<div id="intro">
    <div class="yinyang"></div>
    <h2 style="margin-top:20px;">Carregando...</h2>
</div>

<div id="content">
    Bem-vindo ao site
</div>

<script>
setTimeout(() => {
    document.getElementById("intro").style.opacity = "0";
    
    setTimeout(()=>{
        document.getElementById("intro").style.display="none";
        document.getElementById("content").style.display="flex";
        document.body.style.overflow="auto";
    },1000);

},4000);
</script>

</body>
</html>
