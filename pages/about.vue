<template>
  <div class="about" @mousemove="moveEyes">
    <div class="picture-frame">
      <img class="harry" src="/frame.png" alt="a picture of the young master" />
    </div>
    <div class="face">
      <div class="eyes">
        <div class="eye"></div>
        <div class="eye"></div>
        <div class="moustache"></div>
      </div>
    </div>
    <div class="fireplace">
      <img
        src="https://media1.giphy.com/media/3o72FhIuVWddxQHftS/giphy.gif?cid=790b76114b15859bcd046628fd891d95b39365010355d38b&rid=giphy.gif"
        alt="fireplace of CodeChung Manor"
      />
    </div>
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

// document.querySelector("body").addEventListener("mousemove", eyeball);
// function eyeball() {
//   let eye = document.querySelectorAll(".eye");
//   eye.forEach(function(eye) {
//     let x = eye.getBoundingClientRect().left + eye.clientWidth / 2;
//     let y = eye.getBoundingClientRect().top + eye.clientWidth / 2;
//     let radian = Math.atan2(event.pageX - x, event.pageY - y);
//     let rot = radian * (180 / MATH.PI) * -1 + 270;

//     eye.style.transform = "rotate(" + rot + "deg)";
//   });
// }
</script>

<style>
.about {
  background: url("https://image.freepik.com/free-photo/background-old-vintage-dirty-brick-wall-with-peeling-plaster-texture_106569-139.jpg");
  height: calc(100% - 100px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
}

.face {
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
  transform: scale(.7);
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

.fireplace {
  padding-top: 50px;
}

.fireplace img {
  border-radius: 40px;
  width: 420px;
}

.picture-frame {
  align-self: flex-start;
  position: relative;
  top: 20px;
  left: 15%;
}

.harry {
  width: 250px;
}
</style>