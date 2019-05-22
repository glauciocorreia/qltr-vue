<template>
  <div>
    <div class="home-text d-flex justify-content-between align-items-center">
      <div class="home-text-left">
        <span class="home-subtitle">WHAT WE DO?</span>
        <h1 class="home-title">
          We grow
          <br>
          <span class="home-title-highlight">great business</span>
        </h1>
      </div>
      <div class="home-text-right">
        <span>SCROLL TO SEE MORE</span>
      </div>
    </div>
    <div class="home-field-link">
      <p>Velit laoreet id donec ultrices. Ut lectus arcu bibendum varius.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeBody",
  props: [],
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>


.home-text {
	margin: 4% 4%;
}

.home-text div .home-subtitle {
	font-weight: 800;
	font-size: 14.4px;
	line-height: 30px;
	letter-spacing: 4px;
	text-transform: uppercase;
	color: #FCFCFC;
}
.home-text div .home-title {
	font-weight: 900;
	font-size: 99px;
	line-height: 118px;
	color: #FCFCFC;
}

.home-text div .home-title .home-title-highlight {
	color: #F61067;
}

.home-text .home-text-right {
	writing-mode: vertical-rl;
	text-orientation: mixed;
	font-weight: 800;
	font-size: 14.4px;
	line-height: 30px;
	letter-spacing: 4px;
	text-transform: uppercase;
	color: #FCFCFC;
}

.home-field-link {
	margin: 4% 48% 4% 0;
	padding: 2% 2% 2% 4%;
	border-top: 1px solid #FCFCFC;
	border-right: 1px solid #FCFCFC;
	border-bottom: 1px solid #FCFCFC;

}

.home-field-link p {
	color: #FCFCFC;
}

</style>
