<template>
  <div>
    <button class="menu-toggle" @click="abrir"></button>
    <nav>
      <ul class="menu">
        <li data-text="Home">Home</li>
        <li data-text="Services">Services</li>
        <li data-text="Work">Work</li>
        <li data-text="About">About</li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
    data () {
        return {
            buttonClicked: false
        }
    },
    methods: {
        abrir() {
            const el = document.querySelector('body');

            this.buttonClicked = !this.buttonClicked;
            
            this.buttonClicked == true ? el.classList.add("open") : el.classList.remove("open");
        }
    }
};
</script>

<style lang="scss" scoped>

ul {
  list-style: none;
  margin: 0;
  padding: 0;

  li {
    cursor: pointer;
    padding: 0.8vh 1.4vw;
    font-size: 4.5vw;
  }
}

button {
    background-color: transparent;
    position: relative;
    z-index: 2;
    border: none;
    width: 36px;
    height: 25px;
    outline: none;
    -webkit-transition: opacity 0.2s ease-out;
    transition: opacity 0.2s ease-out;

  &:before {
    content: "";
    @include position-center;
    right: auto;
    width: 100%;
    background: linear-gradient(
      to bottom,
      $primary-color,
      $primary-color 20%,
      transparent 20%,
      transparent 40%,
      $primary-color 40%,
      $primary-color 60%,
      transparent 60%,
      transparent 80%,
      $primary-color 80%,
      $primary-color 100%
    );
    transition: opacity 0.2s ease-out, width 0.2s 0.2s ease-out;
  }

  &:after {
    opacity: 0;
    content: "×";
    color: white;
    position: absolute;
    top: 16px;
    left: -4px;
    font-family: Arial, sans-serif;
    font-size: 76px;
    line-height: 0;
    transition: opacity 0.4s ease-out;
  }
  &:active {
    transform: translateY(2px);
  }
  &:hover {
    opacity: 1;
    cursor: pointer;
  }
  .open & {
    opacity: 1;
    &:before {
      opacity: 0;
      width: 0;
    }
    &:after {
      opacity: 1;
      transform: translate3d(0, 0, 0) rotate(360deg);
      transition: transform 0.4s 1s ease-out, opacity 0.4s 1s ease-out;
    }
  }
}

nav {
  z-index: 1;
  position: fixed;
  top: -100%;
  left: 0;
  width: 100%;
  height: 100%;
  transform: translate3d(0, 0, 0);
  backface-visibility: hidden;
  overflow: hidden;
  &:before {
    content: "";
    @include position-center;
    background: rgba($background-color, 0.9);
    width: 100%;
    height: 0;
    padding-bottom: 100%;
    transform: scale(0.04), translateY(9999px);
    overflow: hidden;
  }
  .open & {
    top: 0;
    &:before {
      animation: menu-animation 0.8s ease-out forwards;
    }
  }
}

ul.menu {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate3d(-50%, -50%, 0);
  backface-visibility: hidden;
  perspective: 1000;
  color: white;
  li {
    opacity: 0;
    text-align: center;
    transform: translate3d(0, 36px, 0);
    &:before {
      content: "";
      @include position-center;
      left: auto;
      background-color: white;
      height: 100%;
      width: 0;
      overflow: hidden;
      transition: width 0.14s ease-out;
    }
    &:after {
      opacity: 0;
      content: attr(data-text);
      @include position-center;
      color: $background-color;
      overflow: hidden;
      transform: translate(-24px, 6px);
      transition: transform 0.1s ease-out, opacity 0.1s ease-out;
    }
    &:hover {
      &:before {
        left: 0;
        right: auto;
        width: 100%;
      }
      &:after {
        opacity: 1;
        padding: 0 20px;
        transform: translate(0px, 6px);
        transition: transform 0.2s 0.14s ease-out, opacity 0.2s 0.14s ease-out;
      }
    }
    .open & {
      opacity: 1;
      transform: translate3d(0, 0, 0);
      transition: transform 0.2s ease-out, opacity 0.2s ease-out;
      @for $i from 1 to 5 {
        &:nth-child(#{$i}) {
          transition-delay: $i * 0.1s + 0.65s;
        }
      }
    }
  }
}
</style>
