<template>
  <div class="portfolio">
    <h1>
      Port
      <span style="color:#bfd5ff;">folio</span>
    </h1>
    <div class="carousel">
      <div class="project-card">
        <nuxt-link :to="'/portfolio/facejams'">
          <img src="/facejams.jpeg" alt="face jams" />
        </nuxt-link>
      </div>
      <div class="project-card">
        <nuxt-link :to="'/portfolio/goala'">
          <img src="/goala.png" alt="goala" />
        </nuxt-link>
      </div>
      <div class="project-card">
        <nuxt-link :to="'/portfolio/fridgefriend'">
          <img src="/fridgefriend.png" alt="fridge friend" />
        </nuxt-link>
      </div>
      <div class="project-card">
        <nuxt-link :to="'/portfolio/noodlebox'">
          <img src="/noodlebox.jpg" alt="noodlebox" />
        </nuxt-link>
      </div>
      <div class="project-card">
        <nuxt-link :to="'/portfolio/mydayspa'">
          <img src="/fridgefriend.png" alt="my day spa" />
        </nuxt-link>
      </div>
      <div class="project-card">
        <nuxt-link :to="'/portfolio/eatos'">
          <img src="/fridgefriend.png" alt="eatos" />
        </nuxt-link>
      </div>
      <div class="project-card">
        <nuxt-link :to="'/portfolio/networkkm'">
          <img src="/fridgefriend.png" alt="network km" />
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Portfolio",
      meta: [
        {
          hid: "portfolio",
          name: "portfolio",
          content: "Whoa check out Harrys projects"
        }
      ]
    };
  },
  components: {}
};
</script>

<style>
.portfolio {
  padding-top: 30px;
  max-width: 90%;
  margin: 0 auto;
  box-sizing: border-box;
}

.carousel {
  display: flex;
  flex-flow: wrap;
  justify-content: center;
  align-items: center;
}

.project-card {
  margin: 10px;
  width: 25%;
  box-sizing: border-box;
  border-radius: 4px;
}

.project-card img {
  width: 100%;
}
</style>