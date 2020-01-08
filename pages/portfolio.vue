<template>
  <div class="portfolio">
    <h1>
      Port
      <span style="color:#bfd5ff;">folio</span>
    </h1>
    <div class="carousel">
      <div class="project-card">
        <img src="/facejams.jpeg" alt="face jams" />
      </div>
      <div class="project-card">
        <img src="/goala.png" alt="goala" />
      </div>
      <div class="project-card">
        <img src="/fridgefriend.png" alt="fridge friend" />
      </div>
      <div class="project-card">
        <img src="/noodlebox.jpg" alt="noodlebox" />
      </div>
      <div class="project-card">
        <img src="/fridgefriend.png" alt="my day spa" />
      </div>
      <div class="project-card">
        <img src="/fridgefriend.png" alt="eatos" />
      </div>
      <div class="project-card">
        <img src="/fridgefriend.png" alt="network km" />
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
}

.project-card img {
    width: 100%;
}
</style>