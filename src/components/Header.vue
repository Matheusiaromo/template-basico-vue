<template>
  
  <header>
    <nav :class="{active2: isActive}">
      <a href="">LOGO</a>
      <button  
      aria-controls="menu" 
      aria-expanded="false" 
      class="burguer" 
      @click="isActive = !isActive">
    <span id="hamburguer"></span></button>
      <ul :class="{active: isActive}" id="menu">
        <li><a>Home</a></li>
        <li><a>Portfolio</a></li>
        <li><a>Sobre</a></li>
        <li><a>Contato</a></li>
      </ul>
    </nav>
  </header>

</template>

<script>
export default {
    data() {
      return {
        isActive: false
      }
    }
}
</script>

<style scoped>

header {
  margin: 0 auto;
  box-shadow: 0px 0px 4px rgba(30, 60, 90, .2);
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0px 10px;
  height: 70px;
}

a {
  padding: 1rem;
  cursor: pointer;
  display: block;
}

li a:hover {
  background: #42b983;
  color: #ffffff;
}

ul {
  display: flex;
  flex-direction: row;
  list-style: none;
}

.burguer {
  display: none;
}


@media (max-width: 630px)
{

  button {
    display: flex;
    padding: 0.5rem 1rem;
    font-size: 1rem;
    border: none;
    background: none;
    cursor: pointer;
    gap: 0.5rem;
  }

  nav {
    background-color: #ffffff;
  }
  .burguer
   {
    display: block;
    cursor: pointer;
   }

  #hamburguer {
    border-top: 4px solid #42b983;
    display: block;
  }

  #hamburguer:after,
  #hamburguer:before
   {
    margin-top: 4px;
    content: "";
    display: block;
    width: 30px;
    height:4px;
    background-color: #42b983;
    transition: 0.3s;
    position: relative;
  }

   nav.active2 #hamburger {
    border-top-color: transparent;
  }
  nav.active2 #hamburger:before {
    transform: rotate(135deg);
  }
  nav.active2 #hamburger:after {
    transform: rotate(-135deg);
    top: -7px;
  }

   ul {
     transition: .3s;
     position: absolute;
     top: 72px;
     left: -100%;
     flex-direction: column;
     background-color: #ffffff;
     z-index: 999;
    
   }

   ul li a {
     width: 100vw;
     text-align: center;
     border-bottom: 1px solid rgba(30, 60, 90, .1);
     border-right: 1px solid rgba(30, 60, 90, .1);
   }

    .active {
     left: 0;
   }


}

</style>

