<template>
	<main id="app">
		<TheHeader/>
		<TheMasthead/>
		<TheJumpNav/>
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
						<div class="c-col c-col-card u-yellow-bg c-col-card--normal c-col--has-bg-color c-col-card--has-link" >
					        <div class="c-col-card__wrap">
					            <figure class="c-col-card__fig c-col-image__fig--crop c-col-image__fig--16x10-crop lazyloaded">
						            <img src="https://source.unsplash.com/random/1600x1000/?animal,landscape">
					        	</figure>
						        <a class="c-col-card__link" target="" href="" tabindex="0" role="button">
						            <span class="u-hidden-visually">Construkt Cards</span>
						        </a>
								<div class="c-col-card__content">
						            <div class="c-col-card__text">
										<div class="c-col-text-area">
						                    <h2 class="c-col-title">This is a card title</h2>
											<p><span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</span></p>
						                </div>
									</div>
									<div class="c-col-card__buttons">
						                <span class="c-cta">Construkt Cards</span>
									</div>
						        </div>
						    </div>
					    </div>
					</div>
					<div class="o-grid__cell u-1/3@desktop">
						<div class="c-col c-col-card u-blue-bg c-col-card--normal c-col--has-bg-color c-col-card--has-link" >
					        <div class="c-col-card__wrap">
					            <figure class="c-col-card__fig c-col-image__fig--crop c-col-image__fig--16x10-crop lazyloaded">
						            <img src="https://source.unsplash.com/random/1600x1000/?animal,landscape">
					        	</figure>
						        <a class="c-col-card__link" target="" href="" tabindex="0" role="button">
						            <span class="u-hidden-visually">Construkt Cards</span>
						        </a>
								<div class="c-col-card__content">
						            <div class="c-col-card__text">
										<div class="c-col-text-area">
						                    <h2 class="c-col-title">This is a card title</h2>
											<p><span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</span></p>
						                </div>
									</div>
									<div class="c-col-card__buttons">
						                <span class="c-cta">Construkt Cards</span>
									</div>
						        </div>
						    </div>
					    </div>
					</div>
					<div class="o-grid__cell u-1/3@desktop">
						<div class="c-col c-col-card u-red-bg c-col-card--normal c-col--has-bg-color c-col-card--has-link" >
					        <div class="c-col-card__wrap">
					            <figure class="c-col-card__fig c-col-image__fig--crop c-col-image__fig--16x10-crop lazyloaded">
						            <img src="https://source.unsplash.com/random/1600x1000/?animal,landscape">
					        	</figure>
						        <a class="c-col-card__link" target="" href="" tabindex="0" role="button">
						            <span class="u-hidden-visually">Construkt Cards</span>
						        </a>
								<div class="c-col-card__content">
						            <div class="c-col-card__text">
										<div class="c-col-text-area">
						                    <h2 class="c-col-title">This is a card title</h2>
											<p><span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</span></p>
						                </div>
									</div>
									<div class="c-col-card__buttons">
						                <span class="c-cta">Construkt Cards</span>
									</div>
						        </div>
						    </div>
					    </div>
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