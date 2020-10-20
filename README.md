<html lang="en"><link type="text/css" rel="stylesheet" id="dark-mode-general-link"><link type="text/css" rel="stylesheet" id="dark-mode-custom-link"><style type="text/css" id="dark-mode-custom-style"></style><head>

  <meta charset="UTF-8">
  
<link rel="apple-touch-icon" type="image/png" href="https://static.codepen.io/assets/favicon/apple-touch-icon-5ae1a0698dcc2402e9712f7d01ed509a57814f994c660df9f7a952f3060705ee.png">
<meta name="apple-mobile-web-app-title" content="CodePen">

<link rel="shortcut icon" type="image/x-icon" href="https://static.codepen.io/assets/favicon/favicon-aec34940fbc1a6e787974dcd360f2c6b63348d4b1f4e06c77743096d55480f33.ico">

<link rel="mask-icon" type="" href="https://static.codepen.io/assets/favicon/logo-pin-8f3771b1072e3c38bd662872f6b673a722f4b3ca2421637d5596661b4e2132cc.svg" color="#111">


  <title>CodePen - Deadpool Movie Card UI</title>
  
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/5.0.0/normalize.min.css">

  
  
<style>
@import url(https://fonts.googleapis.com/css?family=Lato:400,300,700);
@import url(https://fonts.googleapis.com/css?family=Rubik:400,900);

*{box-sizing: border-box;}
body, html { height: 100%; min-height: 100%; }
body {
   background: -webkit-gradient(linear, left top, left bottom, from(#f6f7fc), color-stop(40%, #d5e1e8));
   background: linear-gradient(#f6f7fc 0%, #d5e1e8 40%);
   -webkit-transform-style: preserve-3d;
           transform-style: preserve-3d;
   -webkit-transform: perspective(800px);
           transform: perspective(800px);
   font-family: 'Lato', sans-serif;
}

#card-container{
   width: 700px;
   height: 350px;
   position:absolute;
   top: 50%; left: 50%;
   margin: -175px 0 0 -350px;
}
#card{
   -webkit-animation: backAn 60s infinite;
           animation: backAn 60s infinite;
   color:#fff;
   padding:30px;
   width:100%;
   height:100%;
   position:absolute;
   z-index:1;
 background:url(http://riccardotartaglia.it/img/deadpool/back.jpg) 100% bottom;
   box-shadow: 
     0px 45px 100px rgba(0, 0, 0, .4),
     inset 0 0 0 1000px rgba(156,27,27,.6);
}

#card .text-block{position:relative;z-index:2;text-shadow: 0px 3px 10px rgba(0, 0, 0, .7)}
#card .text-block h1{font-family: 'Rubik', sans-serif; font-size:3em; margin:0; text-transform:uppercase; font-weight:700;}
#card .text-block h1 small{font-size:.4em;color:#ccc;position:relative;bottom:10px}
#card .text-block h3{margin:0;font-weight:700;}
#card .text-block p{font-weight:300; width:60%}
#card .text-block button{-webkit-transition: all .35s cubic-bezier(.37,.26,.35,1);transition: all .35s cubic-bezier(.37,.26,.35,1);border:4px solid #fff; padding:10px; background:transparent;font-family: 'Rubik', sans-serif;text-transform:uppercase; font-weight:700; cursor:pointer;}
#card .text-block button:hover{background:#B51D2A}

#card-container .pg{position:absolute;height:450px; width:40%; right:-10px;bottom:0px;z-index:2}
#card-container .pg > img{height:450px;}

.shine {
position: absolute;
top: 0; left: 0; right: 0; bottom: 0;
background: -webkit-gradient(linear, left top, right top, from(rgba(0,0,0,.4)),color-stop(60%, rgba(0,0,0,.2)));
background: linear-gradient(90deg, rgba(0,0,0,.4) 0%,rgba(0,0,0,.2) 60%);
z-index: 1;
}
button{color:#fff;}

@-webkit-keyframes backAn {
  0%   { background-size:100% }
  50%   { background-size:250% }
  100%   { background-size:100% }
}

@keyframes backAn {
  0%   { background-size:100% }
  50%   { background-size:250% }
  100%   { background-size:100% }
}
</style>

  <script>
  window.console = window.console || function(t) {};
</script>

  
  
  <script>
  if (document.location.search.match(/type=embed/gi)) {
    window.parent.postMessage("resize", "*");
  }
</script>


</head>

<body translate="no">
  <div id="card-container" data-offset="2" style="transform: translateY(0.5px) rotateX(-0.334737deg) rotateY(-1deg);">
   <div class="pg">
      <img src="http://riccardotartaglia.it/img/deadpool/deadpool.png">
   </div>
   <div id="card">
      <div class="shine" style="background: linear-gradient(260.596deg, rgba(0, 0, 0, 0.067) 0%, rgba(0, 0, 0, 0.25) 80%);"></div>
      <div class="text-block">
         <h1>Deadpool <small>(2016)</small></h1>
         <h3>Action, Adventure, Sci-Fi</h3>
         <p>
            Deadpool is a 2016 American superhero film based on the Marvel Comics character of the same name. It is the eighth installment of the X-Men film series, and is directed by Tim Miller.
         </p>
         <button>Watch Trailer</button>
      </div>
   </div>
</div>
    <script src="https://static.codepen.io/assets/common/stopExecutionOnTimeout-157cd5b220a5c80d4ff8e0e70ac069bffd87a61252088146915e8726e5d9f147.js"></script>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
  
      <script id="rendered-js">
var $poster = $('#card-container'),
$shine = $('.shine'),
w = $(window).width(),
h = $(window).height();

$(window).on('mousemove', function (e) {
  var offsetX = 0.5 - e.pageX / w,
  offsetY = 0.5 - e.pageY / h,
  dy = e.pageY - h / 2,
  dx = e.pageX - w / 2,
  theta = Math.atan2(dy, dx),
  angle = theta * 180 / Math.PI - 90,
  offsetPoster = $poster.data('offset'),
  transformPoster = 'translateY(' + -offsetX * offsetPoster + 'px) rotateX(' + -offsetY * offsetPoster + 'deg) rotateY(' + offsetX * (offsetPoster * 2) + 'deg)';

  if (angle < 0) {
    angle = angle + 360;
  }
  $shine.css('background', 'linear-gradient(' + angle + 'deg, rgba(0,0,0,' + e.pageY / h / 5 + ') 0%,rgba(0,0,0,.25) 80%)');

  $poster.css('transform', transformPoster);
});
//# sourceURL=pen.js
    </script>

  




 
</body></html>
