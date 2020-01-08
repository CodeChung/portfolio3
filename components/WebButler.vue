<template>
  <div class="butler" @mousemove="moveEyes">
    <div class="face">
      <div class="eyes">
        <div class="eye"></div>
        <div class="eye"></div>
        <div class="moustache"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "WebButler",
  methods: {
    moveEyes() {
      let eye = document.querySelectorAll(".eye");
      eye.forEach(function(eye) {
        let x = eye.getBoundingClientRect().left + eye.clientWidth / 2;
        let y = eye.getBoundingClientRect().top + eye.clientWidth / 2;
        let radian = Math.atan2(event.pageX - x, event.pageY - y);
        let rot = radian * (180 / Math.PI) * -1 + 270;

        eye.style.transform = "rotate(" + rot + "deg)";
      });
    }
  }
};
</script>

<style>

.face {
  z-index: 1000;
  position: absolute;
  right: 100px;
  top: 150px;

  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: #ffcd00;
  display: flex;
  justify-content: center;
  align-items: center;
  transform: scale(0.7);
}

.face::before {
  content: "";
  position: absolute;
  top: 180px;
  width: 150px;
  height: 70px;
  background: #b57700;
  transition: 0.5s;
  border-bottom-left-radius: 70px;
  border-bottom-right-radius: 70px;
}

.face:hover::before {
  top: 210px;
  width: 150px;
  height: 20px;
  background: #b57700;
  border-bottom-left-radius: 0px;
  border-bottom-right-radius: 0px;
}

.eyes {
  position: relative;
  top: -40px;
  display: flex;
}

.eyes .eye {
  position: relative;
  width: 80px;
  height: 80px;
  display: block;
  background: #fff;
  margin: 0 15px;
  border-radius: 50%;
}

.eyes .eye::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 25px;
  transform: translate(-50%, -50%);
  width: 40px;
  height: 40px;
  background: #333;
  border-radius: 50%;
}
</style>