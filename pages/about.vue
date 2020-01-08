<template>
  <div class="about">
    <section class="zoom">
      <img src="/mountain1.png" alt="peak mountain" id="layer1" />
      <img src="/mountain2.png" alt="peak mountain" id="layer2" />
      <img src="/text.png" alt="adventure time text" id="text" />
    </section>
    <section class="content">
      <h2>Howdy</h2>
      <p>My name is Harry Chung</p>
    </section>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About the App",
      meta: [
        {
          hid: "about",
          name: "about",
          content:
            "Oh please come in and rest at the manor. You must, you must my liege. What do you wish to know about CodeChung?"
        }
      ]
    };
  },
  created() {
    if (process.browser) {
      window.addEventListener("scroll", this.handleScroll);
    }
  },
  mounted() {
    window.onscroll = () => {
      console.log("scrolling");
      if (
        document.documentElement.scrollTop > 0 ||
        document.body.scrollTop > 0
      ) {
        console.log('hgvc')
      }
    };
  },
  methods: {
    handleScroll() {
      console.log(window.scrollY);
    },
    scrollMountain() {
      console.log("bonionj");
      let layer1 = document.getElementById("layer1");
      scroll = window.pageYOffset;

      document.addEventListener("scroll", function(e) {
        let offset = window.pageYOffset;
        scroll = offset;
        layer1.style.width = 100 + scroll / 5 + "%";
      });

      let layer2 = document.getElementById("layer2");
      scroll = window.pageYOffset;

      document.addEventListener("scroll", function(e) {
        let offset = window.pageYOffset;
        scroll = offset;
        layer2.style.width = 100 + scroll / 5 + "%";
        layer2.style.left = scroll / 50 + "%";
      });
    }
  }
};
</script>

<style>
.about {
  margin: 0;
  padding: 0;
}

.zoom {
  width: 100%;
  height: 1000px;
  position: relative;
  overflow: hidden;
  background: url("../static/bg.jpg");
  background-size: cover;
}

.zoom:before {
  content: "";
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 200px;
  z-index: 1000;
  background: linear-gradient(transparent, #fff);
}

.zoom #layer1 {
  position: absolute;
  left: 40%;
  width: 100%;
  transform: translateX(-50%);
  z-index: 10;
}

.zoom #layer2 {
  position: absolute;
  right: 0;
  width: 100%;
  z-index: 9;
}

.zoom #text {
  position: absolute;
  right: 0;
  width: 100%;
  transform: translateY(50%);
}

.content {
  padding: 100px;
  box-sizing: border-box;
  font-family: "Courier New", Courier, monospace;
}

.content h2 {
  margin: 0;
  padding: 0;
  font-size: 4em;
}

.content p {
  font-size: 1.2em;
}
</style>