<template>
  <div class="home">
    <div class="home-text d-flex justify-content-between align-items-center">
      <div class="home-text-left">
        <span class="home-subtitle">{{ subtitle }}</span>
        <h1 class="home-title">
          {{ title1 }}
          <br>
          <span class="home-title-highlight">{{ title2 }}</span>
        </h1>
      </div>
      <div class="home-text-right">
        <span>SCROLL TO SEE MORE</span>
      </div>
    </div>
    <div class="home-field-link">
      <p>{{ textLink }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeBody",
  props: {
    subtitle: String,
    title1: String,
    title2: String,
    textLink: String
  },
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
.home {
  .home-text {
    margin: 10vh 4vw;
    color: $primary-color;

    div {
      .home-subtitle {
        font-weight: 800;
        font-size: 1.03vw;
        line-height: 2.3vw;
        letter-spacing: 0.3vw;
        text-transform: uppercase;
      }
      .home-title {
        font-weight: 800;
        font-size: 7.07vw;
        line-height: 7.71vw;

        .home-title-highlight {
          color: $secondary-color;
        }
      }
    }

    .home-text-right {
      writing-mode: vertical-rl;
      text-orientation: mixed;
      font-weight: 800;
      font-size: 1.030vw;
      line-height: 2.1vw;
      letter-spacing: 5px;
      text-transform: uppercase;
    }
  }

  .home-field-link {
    margin: 4vh 48vw 4vh 0;
    padding: 5vh 4vw 5vh 4vw;
    border-top: 1px solid $primary-color;
    border-right: 1px solid $primary-color;
    border-bottom: 1px solid $primary-color;

    p {
      color: $primary-color;
      font-size: 1.030vw;
    }
  }
}
</style>
