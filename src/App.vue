<template>
  <router-view></router-view>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  created() {

    if (window.location.pathname != '/registrar' && window.location.pathname != '/') {
      if (!localStorage.getItem('token')) {
        this.$router.push('/')
      }
    }
    if (window.location.pathname == '/registrar' || window.location.pathname == '/') {
      if (localStorage.getItem('token')) {
        this.$router.push('/inicial')
      }
    }

  }
}
</script>

<style>
@import './assets/fonts/fonts-GoodTimes.css';
@import './assets/fonts/fonts-Poppins.css';

* {
  margin: 0px;
  padding: 0px;
  transition: 0.5s;
  text-decoration: none;
  font-family: Poppins-Regular;
}

body {
  width: 100%;
}


a {
  color: white;
}

a:link {
  text-decoration: none;
}

.color1 {
  color: #000000;
}

.color2 {
  color: #032541;
}

.color3 {
  color: #125d96;
}

.color4 {
  color: #1e9ef7;
}

.color5 {
  color: #1ce6ff;
}

.error-text {
  color: rgb(255, 72, 72);
  font-size: 14px;
  width: 100%;
  display: block;
  text-align: initial;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}

.enviar-mensagem {
  position: fixed;
  bottom: 30px;
  right: 30px;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background-color: #6c757d;
}

.enviar-mensagem:hover {
  background-color: #6c757d;
  box-shadow: 0px 0px 40px 0px rgb(0 0 0 / 31%);
}


@media (max-width: 576px) {

  .enviar-mensagem:hover {
    
    box-shadow: none;
  }

}

@media (max-width: 991.98px) and (min-width:768px) {

  body:not(.sidebar-mini-md):not(.sidebar-mini-xs):not(.layout-top-nav) .content-wrapper,
  body:not(.sidebar-mini-md):not(.sidebar-mini-xs):not(.layout-top-nav) .main-footer,
  body:not(.sidebar-mini-md):not(.sidebar-mini-xs):not(.layout-top-nav) .main-header {
    transition: margin-left .3s ease-in-out;
    margin-left: 250px;
  }
}</style>
