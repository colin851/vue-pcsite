<template>
  <div class="about">
    <div class="cross">
			<span></span>
			<span></span>
		</div>
		<div class="about-text">
			<p>about momo</p>
			<p>design</p>
		</div>
		<div class="about-container">
			<div class="item item1">
				<a class="item1-1"><img src="img/timg.jpg" /></a>
				<a class="item1-2"><img src="img/timg.jpg" /></a>
				<a class="item1-3"><img src="img/timg.jpg" /></a>
				<a class="item1-4"><img src="img/timg.jpg" /></a>
				<a class="center-img"><img src="img/timg.jpg" /></a>
			</div>
			
			<div class="item item2">
				<a class="item2-1"><img src="img/timg.jpg" /></a>
				<a class="item2-2"><img src="img/timg.jpg" /></a>
				<a class="item2-3"><img src="img/timg.jpg" /></a>
				<a class="item2-4"><img src="img/timg.jpg" /></a>
			</div>
			
			<div class="item item3">
				<a class="item3-1"><img src="img/timg.jpg" /></a>
				<a class="item3-2"><img src="img/timg.jpg" /></a>
				<a class="item3-3"><img src="img/timg.jpg" /></a>
				<a class="item3-4"><img src="img/timg.jpg" /></a>
			</div>
		</div>
		
		
		<div class="center-block">
			
			<span class="pure-text">vacancies</span>
			<div class="about-describe">
				<p>African expeditionary bomb flew over a land of orient Libya Wednesday, descending digit bombs on an area mostly dominated</p>
			</div>
			
			<div class="position-text">
				<div class="position-item position-item1">
					<span class="position-no">4</span>
					<a class="position-link" href="page.html">
						<span>ui designer</span>
						<span>chengdu</span>
					</a>
				</div>
				<div class="position-item position-item2">
					<span class="position-no">6</span>
					<a class="position-link" href="page.html">
						<span>graphic designer</span>
						<span>tianjin</span>
					</a>
				</div>
				
				<div class="position-item position-item3">
					<span class="position-no">3</span>
					<a class="position-link" href="page.html">
						<span>3d designer</span>
						<span>beijing</span>
					</a>
				</div>
				
				<div class="position-item position-item4">
					<span class="position-no">2</span>
					<a class="position-link" href="page.html">
						<span>ux designer</span>
						<span>beijing</span>
					</a>
				</div>
			</div>
			
		</div>
		
		<a class="email" href="mailto:momouiteam@immomo.com">
			<p>email</p>
			<p>momouiteam@immomo.com</p>
		</a>
  </div>
</template>
<script>
import $ from "jquery";
export default {
  mounted() {
    $("body").on("mousemove", function(e) {
      var offsetX = e.clientX / window.innerWidth - 0.5,
        offsetY = e.clientY / window.innerHeight - 0.5;
      var _left = -40 * offsetX;
      var _top = -40 * offsetY;
      $(".about-container").css({
        top: _top,
        left: _left
      });
    });
  }
};
</script>

<style>
.about{
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
