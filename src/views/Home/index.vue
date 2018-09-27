<template>
<div>
  <div class="loading-block">
			<span class="span1"><i class="slider loading1"></i></span>
			<span class="span2"><i class="slider loading2"></i></span>
			<span class="span3"><i class="slider loading2"></i></span>
			<span class="span4"><i class="slider loading2"></i></span>
			<span class="span5"><i class="slider"></i></span>
		</div>
  <div class="contaniner">
    <div class="swiper-container">
        <div class="swiper-wrapper">
          <div class="swiper-slide">
            <a :style="styleObj" class='slidecontent banner1'>
              <img :src="require('../../assets/img/banner1.png')" />
            </a>
          </div>
          <div class="swiper-slide">
            <a :style="styleObj1" class='slidecontent banner2'>
              <img :src="require('../../assets/img/banner2.png')" />
            </a>
          </div>
        </div>
        <div class="swiper-pagination"></div>
    </div>
  </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Swiper from "swiper";
import "swiper/dist/css/swiper.min.css";
import BScroll from "better-scroll";
import $ from "jquery";
export default {
  name: "home",
  components: {},
  data() {
    return {
      mainslider: false,
      isLoaded: false,
      myswiper: null,
      styleObj: {
        "background-image": require("../../assets/img/banner1.png")
      },
      styleObj1: {
        "background-image": require("../../assets/img/banner2.png")
      }
    };
  },
  created() {},
  mounted() {
    const that = this;
    this.myswiper = new Swiper(".swiper-container", {
      pagination: {
        el: ".swiper-pagination",
        clickable: true,
        autoplay: true,
        loop: true,
        renderBullet: function(index, className) {
          return '<span class="' + className + '"></span>';
        }
      }
    });
    $(".loading-block .span5 i").on("webkitAnimationEnd", function() {
      $(".contaniner").addClass("scaleBanner");
      $(".loading-block").hide();
    });

    $(".loading-block .span5 i").on("animationEnd", function() {
      $(".contaniner").addClass("scaleBanner");
      $(".loading-block").hide();
    });

    $(".loading-block .span4 .slider").on("webkitAnimationEnd", function() {
      $(".span1 .slider").removeClass("loading1");
      $(".span2 .slider").removeClass("loading2");
      $(".span3 .slider").removeClass("loading2");
      $(".span4 .slider").removeClass("loading2");
      if (that.isLoaded) {
        $(".loading-block .span5 .slider").addClass("loading2");
      } else {
        setTimeout(function() {
          $(".span1 .slider").addClass("loading1");
          $(".span2 .slider").addClass("loading2");
          $(".span3 .slider").addClass("loading2");
          $(".span4 .slider").addClass("loading2");
        }, 100);
      }
    });

    $(".loading-block .span4 .slider").on("animationEnd", function() {
      $(".span1 .slider").removeClass("loading1");
      $(".span2 .slider").removeClass("loading2");
      $(".span3 .slider").removeClass("loading2");
      $(".span4 .slider").removeClass("loading2");
      if (that.isLoaded) {
        $(".loading-block .span5 .slider").addClass("loading2");
      } else {
        setTimeout(function() {
          $(".span1 .slider").addClass("loading1");
          $(".span2 .slider").addClass("loading2");
          $(".span3 .slider").addClass("loading2");
          $(".span4 .slider").addClass("loading2");
        }, 100);
      }
    });

    $("img").imgLoad({
      time: 10000,
      callback: function() {
        that.isLoaded = true;
      }
    });
  }
};
</script>
<style>
.swiper-wrapper {
  height: 100%;
}
.slider,
.slider * {
  width: 100%;
  height: 100%;
}
.slide-item {
  float: left;
}
</style>
