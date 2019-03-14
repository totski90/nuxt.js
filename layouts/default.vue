<template>
  <div>
    <TheHeader />
    <div class="container" >
      <!-- style="background: url('http://images6.fanpop.com/image/photos/33200000/Food-food-33299546-1920-1200.jpg'); background-size: cover; background-repeat: no-repeat;" -->
    <main class="main-content">      
      <nuxt />
    </main>
    </div>    
    <div class="footer"></div>
  </div>
</template>

<script>
  
  // import Header from '@/components/Header'
  import TheHeader from '@/components/TheHeader'

  export default {
    components: {
      TheHeader
    }
  }

</script>

<style>
/*html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}*/

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}


/*this is custom which may affect some of the pages contensts*/
* {
  box-sizing: border-box;
}
body {
  font-family: sans-serif, "Lato";
}

.main-content {
  margin-top: 4.5rem;
  margin-bottom: 4rem;
}

.footer {
  background-color: #022d30;
  padding-top: 10px;   
  height: 50px; 
  width: auto;
}

</style>
