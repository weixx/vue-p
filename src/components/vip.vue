<template>
  <div id="main">
  </div>
</template>

<script>
    import screen from '../common-js/screen-adaptation'
    import $ from 'jquery'
    export default {
        name: "vip"
    }
    window.onload = function () {
      // getData()
    }
    function getData(){

      $('#main').css('overflow','hidden')
      $('body').css('background-color','#F2F2F2')

      var k = 3;
      var head = $("<div></div>")
        .css({
          'text-align': 'center',
          'padding-top': '0.6rem'
        }).appendTo($('#main'))
      for (var i = 0;i < 3;i++){
        if((k === 2 && i === 0)||(k === 1 && i === 0)||(k === 1 && i === 1)){
          continue;
        }
        $('<img id="btn-vip'+(i+1)+'">')
          .attr('src',function(){
            if (i === 0) {
              return 'img/bg_vip_default_cj@3x.png'
            }else if (i === 1) {
              return 'img/bg_vip_default_jk@3x.png'
            }else if (i === 2) {
              return 'img/bg_vip_default_zz@3x.png'
            }
          })
          .css({
            width: '1.5rem',
            height: '1.5rem',
            'margin-left': '0.3rem',
            'margin-right': '0.3rem',
            'margin-bottom': '0.2rem'
          }).appendTo(head)

        $("#btn-vip1").click(function(){
          $("#btn-vip1").attr('src','img/bg_vip_cj@3x.png')
          $("#btn-vip2").attr('src','img/bg_vip_default_jk@3x.png')
          $("#btn-vip3").attr('src','img/bg_vip_default_zz@3x.png')
        })
        $("#btn-vip2").click(function(){
          $("#btn-vip1").attr('src','img/bg_vip_default_cj@3x.png')
          $("#btn-vip2").attr('src','img/bg_vip_jk@3x.png')
          $("#btn-vip3").attr('src','img/bg_vip_default_zz@3x.png')
        })
        $("#btn-vip3").click(function(){
          $("#btn-vip1").attr('src','img/bg_vip_default_cj@3x.png')
          $("#btn-vip2").attr('src','img/bg_vip_default_jk@3x.png')
          $("#btn-vip3").attr('src','img/bg_vip_z@3x.png')
        })

      }

      if (k === 2) {
        $("#btn-vip2").attr('src','img/bg_vip_jk@3x.png')
      } else if (k === 1) {
        $("#btn-vip3").attr('src','img/bg_vip_z@3x.png')
      }else{
        $("#btn-vip1").attr('src','img/bg_vip_cj@3x.png')
      }

      var foot = $('<div></div>')
        .css({
          width: '100%',
          height:'100%',
          overflow: 'hidden'
        }).appendTo($('#main'))
      var bodyul = $('<ul></ul>')
        .css({
          width: '300%',
          height:'100%',
          overflow:'hidden'
        }).appendTo(foot)
      for (var i = 0;i < 3;i++) {
        if((k === 2 && i === 0)||(k === 1 && i === 0)||(k === 1 && i === 1)){
          continue;
        }
        var bodyli = $('<li></li>')
          .css({
            'width': '33.33333%',
            'height':'100%',
            'float':'left'
          }).appendTo(bodyul)
        var body = $("<div></div>")
          .css({
            'text-align': 'center'
          }).appendTo(bodyli)
        var bodyHead = $("<div></div>")
          .css({
            'background-color': function(){
              if (i === 0) {
                return '#ff9390';
              }else if (i === 1) {
                return '#fec984';
              }else if (i === 2) {
                return '#74c8fd';
              }
            },
            width: '8.4rem',
            height: '3.6rem',
            margin: '0 auto',
            'border-top-left-radius': '0.2rem',
            'border-top-right-radius': '0.2rem'
          }).appendTo(body)
        var bodyHeadName = $("<div></div>")
          .css({
            'padding-top': '0.9rem'
          }).appendTo(bodyHead)
        $("<img />")
          .css({
            'vertical-align':'middle',
            width: '1rem',
            height: '1rem'
          })
          .attr('src',function(){
            if (i === 0) {
              return 'img/ic_vip_chuji1@3x.png'
            }else if (i === 1) {
              return 'img/ic_vip_gaoji1@3x.png'
            }else if (i === 2) {
              return 'img/ic_vip_zhizun1@3x.png'
            }
          })
          .appendTo(bodyHeadName)
        $("<span></span>").text(function(){
          if (i === 0) {
            return '初级会员';
          }else if (i === 1) {
            return '金卡会员';
          }else if (i === 2) {
            return '至尊会员';
          }
        })
          .css({
            'font-size': '0.35rem',
            color: '#FFFFFF',
            'font-size':'0.45rem'
          }).appendTo(bodyHeadName)
        var bodyHeadPrice = $("<div></div>")
          .css({
            'margin-top': '0.15rem',
            'color': '#FFFFFF',
            'font-size': '0.9rem'
          }).appendTo(bodyHead)
        $("<span></span>").text('￥')
          .css({
            'font-size': '0.6rem'
          }).appendTo(bodyHeadPrice)
        $("<span></span>").text('300')
          .css({
            'font-weight': 'bold'
          }).appendTo(bodyHeadPrice)
        $("<span></span>").text('/年')
          .css({
            'font-weight': 'bold'
          }).appendTo(bodyHeadPrice)

        //----------------以上为价格区块
        var bodyContent = $("<div></div>")
          .css({
            'background-color': '#fff',
            width: '8.4rem',
            height: '8.4rem',
            margin: '0 auto',
            'border-bottom-left-radius': '0.2rem',
            'border-bottom-right-radius': '0.2rem',
            'padding-top': '0.6rem'
          }).appendTo(body)
        var bodyContent1 = $("<div></div>")
          .css({
            'padding-top': '0.75rem'
          }).appendTo(bodyContent)
        $('<img src="img/ic_vip_zixun@3x.png"/>')
          .css({
            'margin-right': '0.6rem',
            'vertical-align':'middle',
            position: 'absolute',
            width: '0.5rem',
            height: '0.52rem',
            'margin-left': '-2.8rem'
          }).appendTo(bodyContent1)
        $('<span></span>').text('免费咨询优秀专家')
          .css({
            position: 'absolute',
            'margin-left': '-2rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent1)
        $('<span></span>').text(function(){
          if (i === 0) {
            return '0次';
          }else if (i === 1) {
            return '1次';
          }else if (i === 2) {
            return '2次';
          }
        })
          .css({
            position: 'absolute',
            'margin-left': '2.4rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent1)
        var bodyContent2 = $("<div></div>")
          .css({
            'padding-top': '0.75rem'
          }).appendTo(bodyContent)
        $('<img src="img/ic_vip_youhui@3x.png"/>')
          .css({
            'margin-right': '0.6rem',
            'vertical-align':'middle',
            position: 'absolute',
            width: '0.5rem',
            height: '0.52rem',
            'margin-left': '-2.8rem'
          }).appendTo(bodyContent2)
        $('<span></span>').text('咨询优惠')
          .css({
            position: 'absolute',
            'margin-left': '-2rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent2)
        $('<span></span>').text('')
          .css({
            position: 'absolute',
            'margin-left': '2.4rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent2)
        var bodyContent3 = $("<div></div>")
          .css({
            'padding-top': '0.75rem'
          }).appendTo(bodyContent)
        $('<img src="img/ic_vip_zixun@3x.png"/>')
          .css({
            'margin-right': '0.6rem',
            'vertical-align':'middle',
            position: 'absolute',
            width: '0.5rem',
            height: '0.52rem',
            'margin-left': '-2.8rem'
          }).appendTo(bodyContent3)
        $('<span></span>').text('免费专家会诊')
          .css({
            position: 'absolute',
            'margin-left': '-2rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent3)
        $('<span></span>').text('')
          .css({
            position: 'absolute',
            'margin-left': '2.4rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent3)
        var bodyContent4 = $("<div></div>")
          .css({
            'padding-top': '0.75rem'
          }).appendTo(bodyContent)
        $('<img src="img/ic_vip_youhui@3x.png"/>')
          .css({
            'margin-right': '0.6rem',
            'vertical-align':'middle',
            position: 'absolute',
            width: '0.5rem',
            height: '0.52rem',
            'margin-left': '-2.8rem'
          }).appendTo(bodyContent4)
        $('<span></span>').text('免费体检')
          .css({
            position: 'absolute',
            'margin-left': '-2rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent4)
        $('<span></span>').text(function(){
          if (i === 0) {
            return '0次';
          }else if (i === 1) {
            return '1次';
          }else if (i === 2) {
            return '2次';
          }
        })
          .css({
            position: 'absolute',
            'margin-left': '2.4rem',
            'font-size':'0.5rem'
          }).appendTo(bodyContent4)
        $('<button id="obtain-vip'+(i+1)+'"></button>').text('开通会员')
          .css({
            'background-color': function(){
              if (i === 0) {
                return '#ff9390';
              }else if (i === 1) {
                return '#fec984';
              }else if (i === 2) {
                return '#74c8fd';
              }
            },
            'border': 'none',
            'border-radius': '0.6rem',
            'outline': 'none',
            'width': '4.2rem',
            'height': '1.1rem',
            'font-size': '0.5rem',
            'color': '#fff',
            'margin-top': '-0.33rem',
          }).appendTo(body)
      }

      //购买会员点击
      $('#obtain-vip1').click(function(){
        $('#obtain-vip1').css('background-color','#ffa390')
        bridge.show('1')
      })
      $('#obtain-vip2').click(function(){
        $('#obtain-vip2').css('background-color','#fed984')
        bridge.show('2')
      })
      $('#obtain-vip3').click(function(){
        $('#obtain-vip3').css('background-color','#74d8fd')
        bridge.show('3')
      })

      var dom = document.querySelector('ul')
      $('#btn-vip1').click(function(){
        dom.style.transform='translateX('+-(k-3)*dom.children[(k-3)].offsetWidth+'px)';
        dom.style.transition='0.2s all linear';
        iNow = (k-3)
        x=-iNow*dom.children[(k-3)].offsetWidth;
      })
      $('#btn-vip2').click(function(){
        dom.style.transform='translateX('+-(k-2)*dom.children[(k-2)].offsetWidth+'px)';
        dom.style.transition='0.2s all linear';
        iNow = (k-2)
        x=-iNow*dom.children[(k-2)].offsetWidth;
      })
      $('#btn-vip3').click(function(){
        dom.style.transform='translateX('+-(k-1)*dom.children[(k-1)].offsetWidth+'px)';
        dom.style.transition='0.2s all linear';
        iNow = (k-1)
        x=-iNow*dom.children[(k-1)].offsetWidth;
      })

      var oUl=document.querySelector('ul');
      var aLi=oUl.children;
      drag(oUl,aLi[0],k);
    }



    var iNow=0;
    var x=0;
    function drag(oDiv,aLi,pageCount){
      oDiv.addEventListener('touchstart', function(ev){
        var id= ev.targetTouches[0].identifier;
        var disX= ev.targetTouches[0].pageX - x
        var downX=ev.targetTouches[0].pageX;
        function fnMove(ev){
          if(ev.targetTouches[0].identifier==id){
            x=ev.targetTouches[0].pageX - disX;
            oDiv.style.transform='translateX('+x+'px)';
          }
        }
        function fnEnd(ev){
          if(ev.changedTouches[0].identifier==id){
            document.removeEventListener('touchmove',fnMove, false);
            document.removeEventListener('touchend', fnEnd, false);
            oDiv.style.transition='0.2s all linear';
            var upX=ev.changedTouches[0].pageX;
            if(Math.abs(upX-downX)>50){
              if(upX-downX<0){
                iNow++;
                if(iNow == pageCount){
                  iNow = (pageCount - 1);
                }
              }else{
                iNow--;
                if(iNow == -1){
                  iNow = 0;
                }
              }
            }
            oDiv.style.transform='translateX('+-iNow*aLi.offsetWidth+'px)';
            oDiv.addEventListener('transitionend',function(){
              oDiv.style.transition='none';
              x=-iNow*aLi.offsetWidth;
            },false);
            if ((iNow === 0)&&(pageCount === 3)) {
              $("#btn-vip1").attr('src','img/bg_vip_cj@3x.png')
              $("#btn-vip2").attr('src','img/bg_vip_default_jk@3x.png')
              $("#btn-vip3").attr('src','img/bg_vip_default_zz@3x.png')
            }else if (((iNow === 1)&&(pageCount === 3))||((iNow === 0)&&(pageCount === 2))) {
              $("#btn-vip1").attr('src','img/bg_vip_default_cj@3x.png')
              $("#btn-vip2").attr('src','img/bg_vip_jk@3x.png')
              $("#btn-vip3").attr('src','img/bg_vip_default_zz@3x.png')
            }else if (((iNow === 2)&&(pageCount === 3))||((iNow === 1)&&(pageCount === 2))||((iNow === 0)&&(pageCount === 1))) {
              $("#btn-vip1").attr('src','img/bg_vip_default_cj@3x.png')
              $("#btn-vip2").attr('src','img/bg_vip_default_jk@3x.png')
              $("#btn-vip3").attr('src','img/bg_vip_z@3x.png')
            }

          }
        }
        document.addEventListener('touchmove',fnMove, false);
        document.addEventListener('touchend', fnEnd, false);
//      ev.preventDefault();        //事件绑定用的阻止默认事件;
      }, false)
    };
</script>

<style scoped>
  html, body, div, span, applet, object, iframe,
  h1, h2, h3, h4, h5, h6, p, blockquote, pre,
  a, abbr, acronym, address, big, cite, code,
  del, dfn, em, img, ins, kbd, q, s, samp,
  small, strike, strong, sub, sup, tt, var,
  b, u, i, center,
  dl, dt, dd, ol, ul, li,
  fieldset, form, label, legend,
  table, caption, tbody, tfoot, thead, tr, th, td,
  article, aside, canvas, details, embed,
  figure, figcaption, footer, header, hgroup,
  menu, nav, output, ruby, section, summary,
  time, mark, audio, video {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
  }
  /* HTML5 display-role reset for older browsers */
  article, aside, details, figcaption, figure,
  footer, header, hgroup, menu, nav, section {
    display: block;
  }
  body {
    line-height: 1;
  }
  ol, ul {
    list-style: none;
  }
  blockquote, q {
    quotes: none;
  }
  blockquote:before, blockquote:after,
  q:before, q:after {
    content: '';
    content: none;
  }
  table {
    border-collapse: collapse;
    border-spacing: 0;
  }
</style>
