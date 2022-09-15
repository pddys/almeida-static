<template>
	<main id="app">
		<TheHeader/>
		<TheMasthead/>
		<TheJumpNav/>
		<div class="c-container c-container--1200">
			<div class="o-wrapper">
				<div class="o-grid">
					<div class="o-grid__cell u-1/2@desktop">
						<ConstruktCard />
					</div>
					<div class="o-grid__cell u-1/2@desktop">
						<ConstruktCard/>
					</div>
				</div>
			</div>
		</div>
		<div class="c-container u-black-bg c-container--1200">
			<div class="o-wrapper">
				<div class="o-grid">
					<div class="o-grid__cell u-1/2@desktop">
						<ConstruktCard />
					</div>
					<div class="o-grid__cell u-1/2@desktop">
						<ConstruktCard/>
					</div>
				</div>
			</div>
		</div>
		<div class="c-container c-container--1200">
			<div class="o-wrapper">
				<div class="o-grid">
					<div class="o-grid__cell u-1/3@desktop">
						<ConstruktCard />
					</div>
					<div class="o-grid__cell u-1/3@desktop">
						<ConstruktCard/>
					</div>
					<div class="o-grid__cell u-1/3@desktop">
						<ConstruktCard/>
					</div>
				</div>
			</div>
		</div>
		<TheFooter/>
	</main>
</template>

<style scoped lang="scss">
</style>

<script>
export default {
	  mounted () {

		// Detect request animation frame
		var scroll = window.requestAnimationFrame ||
		             // IE Fallback
		             function(callback){ window.setTimeout(callback, 1000/60)};
		var elementsToShow = document.querySelectorAll('.c-col'); 

		function loop() {

		    Array.prototype.forEach.call(elementsToShow, function(element){
		      if (isElementInViewport(element)) {
		        element.classList.add('is-visible');
		      }
		    });

		    scroll(loop);
		}

		// Call the loop for the first time
		loop();

		// Helper function from: http://stackoverflow.com/a/7557433/274826
		function isElementInViewport(el) {
		  // special bonus for those using jQuery
		  if (typeof jQuery === "function" && el instanceof jQuery) {
		    el = el[0];
		  }
		  var rect = el.getBoundingClientRect();
		  return (
		    (rect.top <= 0
		      && rect.bottom >= 0)
		    ||
		    (rect.bottom >= (window.innerHeight || document.documentElement.clientHeight) &&
		      rect.top <= (window.innerHeight || document.documentElement.clientHeight))
		    ||
		    (rect.top >= 0 &&
		      rect.bottom <= (window.innerHeight || document.documentElement.clientHeight))
		  );
		}
	  }
	}
</script>