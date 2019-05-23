<template>
  <header id="#header">
    <nav id="nav-menu" class="d-flex justify-content-between align-items-center">
      <a class="nav-logo" href="#">Looper</a>
      <ul class="nav-list d-flex justify-content-between align-items-center">
        <li v-for="item in navLinks" :key="item.title">
          <a :href="`${ item.href }`">
            <template v-if="item.icon">
              <i :class="`${ item.icon }`"></i>
            </template>
            {{ item.title }}
          </a>
        </li>
      </ul>
      <Menu></Menu>
    </nav>
  </header>
</template>

<script>
import Menu from "@/components/Menu.vue";

export default {
  components: { Menu },
  data() {
    return {
      navLinks: [
        { href: "#", title: "Home" },
        { href: "#", title: "Services" },
        { href: "#", title: "Work" },
        { href: "#", title: "About" },
        { href: "#", title: "(01) 666 - 693 - 456", icon: "fas fa-phone" }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
header {
  padding: 4vh 4vw;

  nav#nav-menu {
    a.nav-logo {
      font-weight: 900;
      font-size: 1.715vw;
      letter-spacing: 0.15vw;
      color: $primary-color;
      transition: transform 0.5s ease-in-out;

      &:hover {
        transform: scale(1.3);
      }
    }

    ul.nav-list {
      width: 50%;

      li {
        font-size: 1.2vw;

        &:after {
          content: "";
          display: block;
          margin: auto;
          height: 1px;
          width: 0px;
          background: transparent;
          transition: width 0.5s ease, background-color 0.5s ease;
        }

        &:hover {
          &:after {
            width: 100%;
            background: darken($primary-color, 10%);
          }
        }

        a {
          &:hover {
            color: darken($primary-color, 10%);
          }
        }
      }
    }
  }
}

a {
  color: $primary-color;
}
</style>
