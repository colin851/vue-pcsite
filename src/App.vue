<template>
  <div id="app">
    
		<div class="logo">
			<span>momo</span>
			<span>design.</span>
		</div>
    <div class="nav">
      <router-link to="/work">work</router-link>
      <router-link to="/about">about</router-link>
      <router-link to="/download">download</router-link>
    </div>
    <div class="contact">
      <a class="contact-way facrbook" href=""><img src="img/facrbook.svg" ></a>
      <a class="contact-way twitter" href=""><img src="img/twitter.svg" ></a>
      <a class="contact-way instagram" href=""><img src="img/instagram.svg" ></a>
    </div>
    <div class="describe">
      <span>2018.04</span>
      <p>first step in thewe are moving</p>
      <p>towards</p>
      <p>design center</p>
    </div>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view />
  </div>
</template>
<script>
import $ from "jquery";
(function($) {
  $.fn.imgLoad = function(options) {
    var opts = $.extend(
      {
        time: 4000, ///等待载入时间，如果超过这个时间就直接执行回调
        callback: function() {} //默认回调
      },
      options
    );
    var $this = this,
      i = 0,
      j = 0,
      len = this.length;
    $this.each(function() {
      var _this = this,
        dateSrc = $(_this).attr("date-src"),
        imgsrc = dateSrc ? dateSrc : _this.src;
      var img = new Image();
      img.onload = function() {
        img.onload = null;
        _this.src = imgsrc;
        i++;
      };
      img.src = imgsrc;
    });
    var t = window.setInterval(function() {
      j++;
      $("#msg").html(i);
      if (i == len || j * 200 >= opts.time) {
        window.clearInterval(t);
        opts.callback();
      }
    }, 200);
  };
})($);
export default {};
</script>

<style>
#app{
  width: 100%;
  height: 100%;
}
@import url("./assets/css/style.css");
</style>
