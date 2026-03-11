<template>

<header>
<h1>Definiciones de Desarrollo Web</h1>
<p>Conceptos básicos de programación web</p>

<button @click="toggleDarkMode">
Modo oscuro
</button>

</header>

<nav>
<a href="#definiciones" class="menu-item">Definiciones</a>
<a href="#ejemplos" class="menu-item">Ejemplos</a>
<a href="#conocenos" class="menu-item">Conócenos</a>
</nav>

<main>

<section id="inicio">
<h2>¿Qué es JavaScript?</h2>
<p>
JavaScript es un lenguaje de programación que permite crear funciones interactivas en las páginas web.
</p>
</section>

<section id="definiciones">

<h2>Definiciones</h2>

<div class="definicion">
<button class="titulo-def" @click="toggle(0)">HTML</button>
<div class="contenido-def" v-show="abierto[0]">
<p>HTML estructura el contenido de una página web.</p>
</div>
</div>

<div class="definicion">
<button class="titulo-def" @click="toggle(1)">CSS</button>
<div class="contenido-def" v-show="abierto[1]">
<p>CSS permite dar estilos, colores y diseño a una página.</p>
</div>
</div>

<div class="definicion">
<button class="titulo-def" @click="toggle(2)">JavaScript</button>
<div class="contenido-def" v-show="abierto[2]">
<p>JavaScript permite crear interactividad en una página web.</p>
</div>
</div>

<div class="definicion">
<button class="titulo-def" @click="toggle(3)">Frontend</button>
<div class="contenido-def" v-show="abierto[3]">
<p>El frontend es la parte visual de una página web que ve el usuario.</p>
</div>
</div>

<div class="definicion">
<button class="titulo-def" @click="toggle(4)">Backend</button>
<div class="contenido-def" v-show="abierto[4]">
<p>El backend es la parte que maneja servidores, bases de datos y lógica.</p>
</div>
</div>

<div class="definicion">
<button class="titulo-def" @click="toggle(5)">Framework</button>
<div class="contenido-def" v-show="abierto[5]">
<p>Un framework es una herramienta que facilita el desarrollo de aplicaciones web.</p>
</div>
</div>

</section>

<section id="ejemplos">

<h2>Ejemplos Interactivos</h2>

<div class="ejemplo">

<h3>Cambiar texto</h3>

<p>{{ mensaje }}</p>

<button @click="cambiarMensaje">
Cambiar mensaje
</button>

</div>


<div class="ejemplo">

<h3>Contador</h3>

<p class="contador">{{ contador }}</p>

<button @click="contador++">➕</button>
<button @click="contador--">➖</button>

</div>


<div class="ejemplo">

<h3>Cambiar color</h3>

<div class="caja" :style="{backgroundColor: color}"></div>

<button @click="cambiarColor">
Cambiar color
</button>

</div>

</section>

<section id="conocenos">
<h2>Conócenos</h2>
<p>Si ves esto el izquierdo es "SOBERBIO"</p>
</section>

</main>

<footer>
<p>© 2025</p>
<p>Desarrollado con 💻</p>
</footer>

</template>


<script>

import { toggleDarkMode } from "vue-dark-toggle"

export default {

data(){
return{

abierto:[false,false,false,false,false,false],

mensaje:"Hola mundo",

contador:0,

color:"blue"

}
},

methods:{

toggleDarkMode,

toggle(i){
this.abierto[i]=!this.abierto[i]
},

cambiarMensaje(){
this.mensaje="Vue hace páginas interactivas 🚀"
},

cambiarColor(){

const colores=["red","blue","green","purple","orange"]

const random=Math.floor(Math.random()*colores.length)

this.color=colores[random]

}

}

}

</script>


<style>
@import "./assets/estilo.css";
</style>