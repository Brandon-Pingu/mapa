<template>
  <header style="display: none !important;">
    <div style="width: 10%;"> logo</div>
    <div class="btn" :style="bwidth" v-for="(button, index) in buttons" :key="index">
      <a role="button">{{ button }}</a>
    </div>
  </header>
  <header>
        <nav class="header__nav">
            <ul class="header__nav__list">
                <li class="nav__list__li" id="btn-marcador-info">
                    Informacion
                </li>
                <li class="nav__list__li" id="btn-marcador-menu">
                    Agregar Marcador
                </li>
                <li class="nav__list__li">
                    elemento
                </li>
                <li class="nav__list__li">
                    elemento
                </li>
                <li class="nav__list__li">
                    elemento
                </li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
  data() {
    return {
      buttons: ["Inicio", "Agregar Marcador", "elemento", "elemento"],
    }
  },
  computed: {
    bwidth() {
      let w;
      w = 90 / this.buttons.length;
      w += "%;";
      return 'width: ' + w;
    }
  }
}

</script>

<style>
/*
header {
  display: flex;
  width: 100%;
  height: 50px;
}
.btn {
  height: 100%;
  background: #ccc;
  transition: .5s;
  transition-property: background;
}
.btn:hover {
  background: #aaa;
}

a{
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  color: #000;
  cursor: pointer;
}*/
:root{
    --main-color: #7a7a7a;
    --hover-color: #acacac;
}

.header__nav{
    display: flex;
    width: 100%;
    height: 7%;
    background-color: var(--main-color);
}

.header__nav__list{
    display: flex;
    justify-content: space-between;
    width: 100%;
    background-color: var(--main-color);
}

.nav__list__li{
    display: flex;
    list-style: none;
    width: 20%;
    /*background-color: var(--main-color);*/
    cursor: pointer;
    transition: .5s;
    transition-property: background;
    justify-content: center;
    align-items: center;
    color: #ffffff;
    /*font-weight: bolder;*/
}

.nav__list__li:hover{
    background-color: var(--hover-color);
}
body{
    min-height: 100vh;
    background-color: var(--color2);
}

.marker{
    background-size: cover;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    position: relative;
}
.marker::before{
    content: '';
    position: absolute;
    display: block;
    opacity: 0;
    transition: 1s;
    width: 0;
    height: 0;
    border-radius: 20px;
    top: 0;
    left: 0;
    background-color: #fcfcfc;
}

.marker:hover::before{
    opacity: 1;
    width: 200px;
    height: 100px;
    top: -100px;
    left: -75px;
}

#map-container{
    position: relative;
}
#map{
    width: 100%;
    height: 70%;
}

.map-info{
    position: absolute;
    background: #fcfcfc;
    width: 20%;
    height: 95%;
    box-shadow: 10px 10px 10px #acacac;
    top: 2.5%;
    left: 2.5%;
    border-radius: 15px;
}

.map-info__card{
    width: 100%;
    height: 100%;
    border-radius: 15px;
    padding: 20px 20px 0;
}

.map-info__card > h2{
    margin: 0 0 20px 0;
}

#filtros{
    width: 100%;
    height: 7%;
    background-color: var(--main-color);
}

#filtros > ul{
    height: 100%;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}

#filtros > ul > li{
    list-style: none;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    width: calc(100% / 12);
    transition: .5s;
    transition-property: background;
    color: #ffffff;
    /*font-weight: bolder;*/
}

#filtros > ul > li:hover{
    background-color: var(--hover-color);
    cursor: pointer;
}

/*cartas*/
#menu-marcador-card > *{
    display: block;
}

#btn-add{
    display: flex !important;
    justify-content: center;
    align-self: center;
    align-items: center;
    margin: 0 auto 15px;
    text-decoration: none;
    color: #000000;
    background-color: #35ADEA;
    border-radius: 17px;
    padding: 5px;
    transition-property: background;
    transition: 0.7s;
}


#grilla-iconos{
    display: grid !important;
    width: 100%;
    height: 40%;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(auto, 40px);
    row-gap: 10px;
    overflow: auto;
    border-radius: 10px;
    background-color: #00000011;
}
.icon{
    width: 40px;
    height: 40px;
    cursor: pointer;
    border-radius: 5px;
    padding: 4px;
    transition: .5s;
}

.icon:hover{
    background: #00000011;
}


#btn-add:hover{
    background-color: #0e8ed8;
}

#menu-marcador-card > label{
    margin: 0 0 10px;
}

#menu-marcador-card > input{
    margin: 0 0 20px;
}
</style>