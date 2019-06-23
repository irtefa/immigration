<template>
  <div id="app">
    <div id="header">The Employment Based Immigration Interview Practice</div>
    <Home question="Welcome to your employment based green card interview."/>
    <div id="footer">
      <a href="/about.html" id="footer-item" target="_blank">About the website</a>
      <div id="disclaimer">Disclaimer: This is a private web site and is NOT affiliated with any government agency. The information provided in this web site is of a general nature and offered for informational purposes only; it is not offered as and does not constitute legal advice. The information may not apply to any particular set of facts or circumstances..</div>
    </div>
  </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'app',
  components: {
    Home
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #002868;
  margin-top: 200px;
}

#disclaimer {
  font-size: 10px;
  color: white;
}

#header {
   position:fixed;
   left:7px;
   top:7px;
}

#footer {
   position:fixed;
   left:0px;
   bottom:0px;
   height:55px;
   width:100%;
   background:#002868;
}

/* IE 6 */
* html #footer {
   position:absolute;
   top:expression((0-(footer.offsetHeight)+(document.documentElement.clientHeight ? document.documentElement.clientHeight : document.body.clientHeight)+(ignoreMe = document.documentElement.scrollTop ? document.documentElement.scrollTop : document.body.scrollTop))+'px');
}

#footer-item {
  color: white;
  padding: 70px;
}

#footer-item:hover {
  color: #BF0A30;
}

#wrapper {
  font-size: 20px;
}

#next-btn {
  display: inline-block;
  background-color: #BF0A30;
  color: white;
  padding-left: 10px;
  padding-right: 10px;
  border-radius: 2px;
  font-size: 30px;
}
</style>
