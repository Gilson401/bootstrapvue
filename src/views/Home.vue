<template>
  <div class="grid-container">
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

    <main class="content">

      <section v-for="comp in links" :key="comp.route" :ref="comp.route">
        <component  v-bind:is="comp.component" />
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
        { label: "/O que fazemos", route: "fazemos", component: CaseGames },
        // { label: "/News", route: "news" },
        // { label: "/Nossos Clientes", route: "clientes" },
        { label: "/Contato", route: "contato", component: Contact },
      ],
    };
  },
  components: { QuemSomos, CaseGames },
  methods: {
    scrollToAnchorPoint(refName) {
      const el =  this.$refs[refName][0];
      el.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>
<style>
.grid-container {
  display: grid;
  grid-template-areas: "menu content";
  grid-template-columns: 15% 85%;
  background-color: rgb(30, 30, 30);
  height: 100vh;
}

.menu {
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

.content{
    padding-left: 30px;
}
</style>
