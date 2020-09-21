<template>
  <div id="app">
    <nasa></nasa>
  </div>
</template>

<script>
import Nasa from './components/Nasa'

export default {
  name: 'app',
  components: {
    Nasa
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #dd0f13;
  margin-top: 60px;
  background:url('https://eus-www.sway-cdn.com/s/ujAWagQ9KE5I89Ga/images/Dfm6RgPmpR40NI?quality=480&allowAnimation=true');
  background-position:bottom;
  font-family: 'Grandstander', cursive;

  
  background-repeat: cover;
}
</style>