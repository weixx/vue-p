<template>
  <div id="app">
    <div id="header">
      <p>远程医疗会诊系统</p>
    </div>
    <div id="content">
      <div id="doctor-list">

      </div>
      <div id="div1">

      </div>
    </div>
    <div id="footer">

    </div>
  </div>
</template>

<script>
  import axios from 'axios'
  import $ from 'jquery'
  export default {
    methods: {

      //startHacking () {
      // this.$notify({
      //   title: 'It works!',
      //   type: 'success',
      //   message: 'We\'ve laid the ground work for you. It\'s time for you to build something epic!',
      //   duration: 5000
      // })
      // }
    }
  }

  window.onload = function () {
    getData()
  }

  function getData() {
    axios.get('/api/v1.0/doctor/consultExpert/list', {
    }).then(function (response) {
      $("<ul id='doctor-list-ul'></ul>")
        .css({
          'height':'600px',
          'overflow':'auto'
        })
        .appendTo($('#doctor-list'))
      console.log(response.data)
      if(response.data.result === 200){
        for (var i = 0;i<response.data.info.length;i++){
          var en = response.data.info[i];
          $("<li>"+en.name+"</li>")
            .css({
              'list-style-type':'none',
              'line-height':'60px',
              'text-align':'center'
            })
            .appendTo($('#doctor-list-ul'))
        }
      }else{
        alert(response.data.error)
      }
    }).catch(function (error) {
      alert(error);
    });
  }
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }

  html{
    overflow-x: hidden;
    overflow-y: hidden;
  }

  #app{
    width: 100%;
    height: 100%;
    position: absolute;
  }
  #header{
    width: 100%;
    height: 12%;
    background: #1282D0;
    margin: auto auto;
    border: 0px solid;
    border-bottom: 2px #d2dfeb;
  }

  #header p{
    color: #ffffff;
    font-size: 28px;
    width: 100%;
    text-align: center;
    padding-top: 1.5%;
    font-weight: bold;
  }

  #content{
    width: 100%;
    height: 83%;
    margin: auto auto;
  }
  #doctor-list{
    width: 200px;
    height: 100%;
    background: #FFFFFF;
    float: left;
    border-style: solid; border-width: 0px 2px 0px 0px;
    border-right-color: #d2dfeb;
  }
  #div1{
    width: 580px;
    height: 100%;
    background: #FFFFFF;
    float: left;
  }

  #footer{
    width: 100%;
    height: 5%;
    background: #1282D0;
    margin: auto auto;
    border-style: solid; border-width: 2px 0px 0px 0px;
    border-top-color: #d2dfeb;
  }

  li:hover{
    background-color: aqua;
  }

  li:active{
    background-color: beige;
  }
</style>
