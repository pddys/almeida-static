<template>
	<header class="c-header" ref="target">
		<div class="c-header__full-container">
			<div class="c-header__container c-header__container--left">
				<div class="c-header__border-top"></div>
				<ul class="c-header__nav c-header__nav--left">
					<li>Menu</li>
					<li>Whats On</li>
					<li>Plan Your Visit</li>
				</ul>
				<div class="c-header__border-bottom"></div>
			</div>
			<video muted playsinline class="c-header__logo" id="c-header__logo">
				<source src="~/assets/img/ALM_Moving_Logo.mp4"
		            type="video/mp4">
			</video>
			<div class="c-header__container c-header__container--right">
				<div class="c-header__border-top"></div>
				<ul class="c-header__nav c-header__nav--right">
					<li>Get Involved</li>
					<li>Support Us</li>
					<li>About Us</li>
				</ul>
				<div class="c-header__border-bottom"></div>
			</div>
		</div>
	</header>
</template>
<style scoped lang="scss">

</style>

<script>
	export default {
	  mounted () {
		const startVideo = async () => {
		  const video = document.querySelector('#c-header__logo');

		  try {
		      await video.play();

		      video.setAttribute('autoplay', true);

		      console.log('video started playing successfully');
		  } catch (err) {
		    console.log(err, 'video play error');
		    // do stuff in case your video is unavailable to play/autoplay
		  }
		}

		setTimeout(startVideo, 2000)
	}
}
</script>