<template>
  <div id="app">
    <Header/>
    <div class="break"></div>
    <router-view  class="full-row" />
  </div> 
</template>

<script>
import Header from './components/layout/header';

export default {
  name: "app",
  components: {
    Header
  }
}
</script>


<style>

  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body{
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    line-height: 1.4;
  }

  #app{
    display: flex;
    flex: 5;
    align-items: center;
    justify-content: center;
    flex-flow: row wrap;
  }

  .container{
    flex: 0.5;
    padding: 20px;
  }

  .about{
    margin-top: 20px;
    display: flex;
    flex: 0.2;
    align-items: center;
    justify-content: center;
    flex-flow: row wrap;
  }

  .break{
    flex-basis: 100%;
    width: 0px; 
    height: 0px; 
    overflow: hidden;
  }

  .btn{
    display: inline-block;
    border: none;
    background: #39a573;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover{
    background: #666;
  }
</style>
