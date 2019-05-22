<template>
  <header id="#header">
    <nav id="nav-menu" class="d-flex justify-content-between align-items-center">
      <a class="nav-logo" href="#">Looper</a>
      <ul class="nav-list d-flex justify-content-between align-items-center">
        <li v-for="item in navLinks" :key="item.title">
          <a :href="`${ item.href }`">{{ item.title }}</a>
        </li>
      </ul>
      <a href="#">Looper</a>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navLinks: [
        { href: "#", title: "Home" },
        { href: "#", title: "Services" },
        { href: "#", title: "Work" },
        { href: "#", title: "About" },
        { href: "#", title: "(01) 666 - 693 - 456" }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>




header {
    padding: 3% 4% 5% 4%;

}
nav {
  a.nav-logo {
    font-weight: 900;
	font-size: 24px;
	line-height: 43px;
	letter-spacing: 2px;
	color: $primary-color;
  }
}
</style>
