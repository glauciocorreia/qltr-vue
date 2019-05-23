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
        <span class="home-text-right-words">SCROLL TO SEE MORE</span>
        <i class="fas fa-arrow-down"></i>
      </div>
    </div>
    <div class="home-field-link d-flex justify-content-between align-items-center">
      <p>{{ textLink }}</p>
      <i class="fas fa-arrow-right"></i>
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
  }
};
</script>

<style lang="scss" scoped>
.home {
  .home-text {
    margin: 10vh 4vw;
    color: $primary-color;
    cursor: default;

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
      font-size: 1.03vw;
      line-height: 2.1vw;
      letter-spacing: 5px;
      text-transform: uppercase;
      transition: transform 0.5s ease-in-out;

      &:hover {
        transform: scale(1.1);
      }

      .home-text-right-words {
        margin-bottom: 2vh;
      }
    }
  }

  .home-field-link {
    margin: 4vh 48vw 4vh 0;
    padding: 5vh 4vw 5vh 4vw;
    border-top: 1px solid $primary-color;
    border-right: 1px solid $primary-color;
    border-bottom: 1px solid $primary-color;
    color: $primary-color;
    font-weight: 800;
    transition: background-color 0.5s ease-in-out, color 0.5s ease-in-out;

    p,
    i {
      font-size: 1.03vw;
    }
    i {
      transform: scale(2);
    }

    &:hover {
      background-color: $primary-color;
      color: $background-color;
      cursor: pointer;
    }
  }
}
</style>
