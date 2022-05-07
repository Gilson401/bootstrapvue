<template>
  <div class="home-container">
    <nav class="menu">
      <div>
        <b-img
          ref="img"
          src="../assets/logo.png"
          fluid-grow
          alt="Fluid-grow image"
        ></b-img>
      </div>

      <ul class="menu-list relative">
        <li
          class="my-3 text-white pr-2 relative d-block"
          v-for="(link, index) in links"
          :key="index"
          @click="scrollToAnchorPoint(link.route)"
        >
          <div class="relative">
            <span
              class="font-size-060 text-gray-300 font-weight-bolder d-block w-100 absolute"
            >
              0{{ index + 1 }}.
            </span>

            <span
              class="text-white text-decoration-none pr-2 absolute z-10 d-block w-100 link"
            >
              {{ link.label }}
            </span>
          </div>
        </li>
      </ul>
    </nav>


<div class="mobile-menu fixed-top">
  <b-navbar class="px-4 w-100" toggleable type="dark" variant="dark">
    <b-navbar-brand href="#">Teu Logo</b-navbar-brand>

    <b-navbar-toggle target="navbar-toggle-collapse">
      <template #default="{ expanded }">
        <b-icon v-if="expanded" icon="chevron-bar-up"></b-icon>
        <b-icon v-else icon="chevron-bar-down"></b-icon>
      </template>
    </b-navbar-toggle>

    <b-collapse id="navbar-toggle-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-item
          v-for="(link, index) in links"
          :key="index"
           :href="`#${link.route}`"> 
           {{ link.label }} 
           </b-nav-item>

      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>

    <main class="content">
      <section  v-for="comp in links" :key="comp.route" :ref="comp.route" :id="comp.route">
        <component v-bind:is="comp.component" />
      </section>
    </main>
  </div>
</template>

<script>
import QuemSomos from "@/components/QuemSomos.vue";
import CaseGames from "@/components/CaseGames.vue";
import Contact from "@/components/Contact.vue";

export default {
  name: "Home",
  metaInfo: {
    title: "YourBusiness",
    titleTemplate: "",
    htmlAttrs: {
      lang: "pt",
      amp: true,
    },
  },
  data() {
    return {
      links: [
        { label: "/Quem Somos", route: "quemsomos", component: QuemSomos },
        { label: "/Projetos", route: "projetos", component: CaseGames },
        { label: "/Contato", route: "contato", component: Contact },
      ],
    };
  },
  components: { QuemSomos, CaseGames },
  methods: {
    scrollToAnchorPoint(refName) {
      const el = this.$refs[refName][0];
      el.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>
<style>

.menu{
    display: none;
}

.mobile-menu{
    display: flex;
    width: 100vw;
}

@media screen and (min-width: 768px) {
    .mobile-menu{
         display: none;
    }
  .home-container {
    display: grid;
    grid-template-areas: "menu content";
    grid-template-columns: 15% 85%;

    height: 100vh;
  }

  .menu {
    display:block;  
    grid-area: menu;
    border-right: 1px solid rgb(62, 62, 62);
  }

  main {
    overflow: hidden;
    overflow-y: auto;
  }

  main::-webkit-scrollbar {
    display: none;
    -ms-overflow-style: none;
    scrollbar-width: none;
  }

  .menu-list {
    list-style: none;
    margin-left: 0;
    text-align: left;
    text-transform: uppercase;
  }

  .row {
    margin-right: 0;
    margin-left: 0;
  }

  li {
    cursor: pointer;
    height: 70px;
  }

  .link {
    top: 33px;

    display: inline-block;
    vertical-align: middle;
    /* transform: translateZ(0); */
    backface-visibility: hidden;
    -moz-osx-font-smoothing: grayscale;
    transition-duration: 0.3s;
    transition-property: transform;
  }

  .link:hover,
  .link:focus,
  .link:active {
    transform: scale(1.1);
  }

  .content {
    padding-left: 30px;
  }
}
</style>
