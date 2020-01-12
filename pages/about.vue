<template>
  <div class="about" @mousemove="moveEyes">
    <h1>Help Desk</h1>
    <div class="butler">
      <div class="face">
        <div class="eyes">
          <div class="eye"></div>
          <div class="eye"></div>
          <div class="moustache"></div>
        </div>
      </div>
    </div>
    <div class="messages">
      <div class="bobert message-chat">
        <p>YOLO</p>
      </div>
      <div class="client message-chat">
        <p>YOWDY</p>
      </div>
    </div>
    <div class="message-input">
      <input type="text" v-model="text" >
      <button>SEND</button>
    </div>
  </div>
</template>

<script>
export default {
  components: {
  },
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
  created() {},
  mounted() {},
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
.about {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  height: calc(100vh - 100px);
  flex-direction: column;
}


.face {
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

.messages {
  width: 60%;
  border-radius: 25px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
  padding: 25px;
  box-shadow: -50px 50px 50px rgba(0, 0, 0, 0.15);
  border: 1px solid #ebebeb;
}

.message-chat {
  width: 100%;
  height: 69px;
  display: flex;
  flex-direction: column;
  font-size: 1.69rem;
}

.bobert {
  justify-content: flex-start;
  align-items: flex-start;
}

.client {
  justify-content: flex-end;
  align-items: flex-end;
}

.message-input {
  height: 119px;
  display: flex;
  justify-content: flex-end;
  width: 60%;
  padding-top: 6.9px;
}

.message-input input {
  height: 39px;
  outline: none;
  width: 60%;
  border-radius: 6.9px;
  border: 1px solid grey;
  padding: 0 10px;
}

.message-input button {
  height: 39px;
  width: 80px;
  margin-right: 5px;
  border-radius: 6.9px;
  outline: none;
}
</style>