<template>
  
  <header id="header">
    <a id="logo" href="">LOGO</a>
    <nav id="nav" :class="{active: isActive}">
     <button @click="isActive = !isActive" aria-label="Abrir Menu" id="btn-mobile" aria-haspopup="true" aria-controls="menu" aria-expanded="false">
        <span id="hamburger"></span>
      </button>
      <ul id="menu" role="menu">
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

#logo {
  padding-left: 1rem;
}

#header {
  box-sizing: border-box;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #ffffff;
  box-shadow: 0px 0px 4px rgba(0, 0, 0, 0.1);
}

#menu {
  display: flex;
  list-style: none;
  gap: 0.5rem;
}

#menu a {
  display: block;
  padding: 0.5rem;
}



#btn-mobile {
  display: none;
}

@media (max-width: 600px) {
  #menu {
    display: block;
    position: absolute;
    width: 100%;
    top: 71px;
    left: 0;
    transform: translate(-20px, 0px);
    background: #ffffff;
    opacity: 0;
    z-index: 1000;
    visibility: hidden;
    overflow-y: hidden;
  }

  #nav.active #menu {
    opacity: 1;
    transform: translate(0px, 0px);
    transition: .3s ease;
    visibility: visible;
    overflow-y: auto;
  }
   #menu li a:hover {
    color: #ffffff;
    background: #42b983;
  }

  #menu li a {
    left: 0;
    text-align: center;
    margin: 0px;

  }

  
 

  #menu a {
    padding: 1rem 0;
    margin: 0 1rem;
    border-bottom: 2px solid rgba(0, 0, 0, 0.05);
  }
  #btn-mobile {
    display: flex;
    padding: 0.5rem 1rem;
    font-size: 1rem;
    border: none;
    background: none;
    cursor: pointer;
    gap: 0.5rem;
  }
  #hamburger {
    border-top: 3px solid #42b983;
    width: 30px;
  }
  #hamburger::after,
  #hamburger::before {
    content: '';
    display: block;
    width: 30px;
    height: 3px;
    background: #42b983;
    margin-top: 5px;
    transition: 0.3s;
    position: relative;
  }
  #nav.active #hamburger {
    border-top-color: transparent;
  }
  #nav.active #hamburger::before {
    transform: rotate(135deg);
  }
  #nav.active #hamburger::after {
    transform: rotate(-135deg);
    top: -7px;
  }
  
  #nav {
    padding: 0px;
  }

}

</style>