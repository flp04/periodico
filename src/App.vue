<!-- <script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script> -->

<template>

  <!-- <div > -->
    <Topo></Topo>

    <div style="margin: 20px 150px 20px 150px">
      <!-- <img @click="irParaHome()" alt="Vue logo" class="logo" src="@/assets/logocabecera-1.png" style="cursor: pointer; margin: 20px 200px 20px 200px;" /> -->
      <img @click="irParaHome()" alt="Vue logo" class="logo" src="@/assets/logocabecera-1.png" style="cursor: pointer;" />
      <img @click="irParaHome()" alt="Vue logo" class="logo" src="@/assets/CELOS-728x90-px.gif" style="cursor: pointer; margin-left: 50px;" />
    </div>
    
    <div class="navbar">
      <div class="menu-invisivel" style="width: 100%; display: flex; justify-content: space-around; align-items: center;">
        <div @click="toggleNavbar" class="menu-toggle" id="mobile-menu">
          <span></span>
          <span></span>
          <span></span>
        </div>

        <img alt="Vue logo" @click="irParaHome()" style="cursor: pointer; width: 150px;" src="@/assets/logocabecera-1.png" />
        <svg style="color: white;" xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16"><path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"/></svg>
      </div>
      <ul class="nav-list">
        <svg @click="irParaHome()" style="color: white" xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="currentColor" class="bi bi-house-door" viewBox="0 0 16 16"><path d="M8.354 1.146a.5.5 0 0 0-.708 0l-6 6A.5.5 0 0 0 1.5 7.5v7a.5.5 0 0 0 .5.5h4.5a.5.5 0 0 0 .5-.5v-4h2v4a.5.5 0 0 0 .5.5H14a.5.5 0 0 0 .5-.5v-7a.5.5 0 0 0-.146-.354L13 5.793V2.5a.5.5 0 0 0-.5-.5h-1a.5.5 0 0 0-.5.5v1.293zM2.5 14V7.707l5.5-5.5 5.5 5.5V14H10v-4a.5.5 0 0 0-.5-.5h-3a.5.5 0 0 0-.5.5v4z"/></svg>
        <li @click="irPara">Local</li>
        <li @click="irPara">Provincia</li>
        <li @click="irPara">Región</li>
        <li @click="irPara">Deportes</li>
        <li @click="irPara">Sociedad</li>
        <li @click="irPara">Cultura y Ocio</li>
        <li @click="irPara">Blogs</li>
        <li @click="irPara">Especiales</li>
        <li @click="irPara">Multimedia</li>
        <svg @click="mostrarCampoBusca" style="color: white;" xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16"><path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"/></svg>
      </ul>
    </div>
    <div class="buscar text-center" style="background-color: white; z-index: 3; position: absolute; border-top: 2px solid red; padding: 10px; display: none; margin-left: 80%;">
      <input type="text">
      <button>Buscar</button>
    </div>

  <RouterView @irParaHome="irParaHome" :secao="secao"/>

    
  <!-- </div> -->

</template>
<script>
import { RouterView } from 'vue-router'
import Topo from './components/Topo.vue'
// import { Conteudo } from 'vue-router'

export default {
  data() {
    return {
      secao: ''
    }
  },
  components: {
    Topo
  },
  methods: {
    toggleNavbar() {
      var navList = document.querySelector('.nav-list');
      navList.classList.toggle('show');
    },
    irPara(event) {
      this.secao = event.target.textContent
      var navList = document.querySelector('.nav-list');
      navList.classList.remove('show');
    }, 
    irParaHome() {
      this.secao = ''
      var navList = document.querySelector('.nav-list');
      navList.classList.remove('show');
    },
    mostrarCampoBusca() {
      var input = document.querySelector('.buscar');
      if (input.style.display == 'none') {
        input.style.display = 'flex'
      } else {
        input.style.display = 'none'
      }
    }
  },
}
</script>
<style>
  .navbar {
    background-color: #333;
    padding: 15px;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .nav-list {
    list-style: none;
    display: flex;
    justify-content: space-around;
    width: 100%;
    margin: 0px;
    padding: 0px;
    text-transform: uppercase;
  }

  /* .nav-list li {
    margin-right: 20px;
  } */

  .nav-list svg {
    cursor: pointer;
  }

  .nav-list svg:hover {
    border-bottom: red 2px solid
  }

  .nav-list li {
    color: white;
    font-weight: bold;
    display: flex;
    cursor: pointer;
    border-bottom: 2px solid transparent;
  }

  .nav-list li:hover {
    border-bottom-color: red;
  }

  .menu-invisivel img{
    display: none;
  }

  .menu-invisivel svg{
    display: none;
  }

  .menu-toggle {
    display: none;
    flex-direction: column;
    cursor: pointer;
  }

  .menu-toggle span {
    height: 3px;
    width: 25px;
    background-color: white;
    margin: 2px 0;
    display: block;
  }

  .buscar {
    box-shadow: 0px 5px 5px 5px rgba(0, 0, 0, 0.3); /* offsetX offsetY blurRadius color */
  }

  @media screen and (max-width: 768px) {
    .logo {
      display: none;
    }

    .menu-invisivel img{
      display: flex;
    }

    .menu-invisivel svg{
      display: flex;
    }

    .navbar {
      padding: 4px;
    }

    .menu-toggle {
      display: flex;
    }

    .nav-list {
      z-index: 1;
      display: none;
      flex-direction: column;
      width: 100%;
      position: absolute;
      top: 60px;
      left: 0;
      background-color: #333;
      text-transform: capitalize;
      padding: 5px;
    }

    .nav-list svg {
      display: none;
    }

    .nav-list.show {
      display: flex;
    }

    .nav-list li {
      margin: 0;
      text-align: center;
    }
  }
</style>