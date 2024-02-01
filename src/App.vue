<!-- <script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script> -->

<template>

  <!-- <div > -->
    <Topo></Topo>

    <img alt="Vue logo" class="logo" src="@/assets/logocabecera-1.png" style="margin: 20px 200px 20px 200px;" />
    
    <div class="navbar">
      <div class="menu-invisivel" style="width: 100%; display: flex; justify-content: space-around; align-items: center;">
        <div @click="toggleNavbar" class="menu-toggle" id="mobile-menu">
          <span></span>
          <span></span>
          <span></span>
        </div>

        <img alt="Vue logo" style="width: 150px;" src="@/assets/logocabecera-1.png" />
        <svg style="color: white;" xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16"><path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"/></svg>
      </div>
      <ul class="nav-list">
        <li @click="irPara">Local</li>
        <li @click="irPara">Provincia</li>
        <li @click="irPara">Región</li>
        <li @click="irPara">Deportes</li>
        <li @click="irPara">Sociedad</li>
        <li @click="irPara">Cultura y Ocio</li>
        <li @click="irPara">Blogs</li>
        <li @click="irPara">Especiales</li>
        <li @click="irPara">Multimedia</li>
        <svg style="color: white;" xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16"><path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"/></svg>
      </ul>
    </div>

  <RouterView :secao="secao"/>

    
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

  .nav-list li {
    color: white;
    font-weight: bold;
    display: flex;
    cursor: pointer;
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