<template>
  <div class="container">
    <div>
      <h3>view-video-modal</h3>
      <button @click="changeStatusModal()">
        OPEN MODAL
      </button>

      <div class="modal" v-if="isOpened" @click.self="changeStatusModal()">
        <div class="modal-content">
          <p>modal</p>
          <!-- <video
            src="https://www.youtube.com/embed/n5U1zR6SWRE" controls
            width="300" height="168"
            v-playing="isOpened"
          ></video> -->
          <iframe width="300" height="168" src="https://www.youtube.com/embed/n5U1zR6SWRE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpened: false,
    }
  },
  methods: {
    changeStatusModal: function() {
      this.isOpened = !this.isOpened
    }
  },
  // directives: {
  //   playing(el, binding){
  //     binding.value ? el.play() : el.pause();
  //   }
  // },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.modal {
  position: fixed; top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 10;
  background: rgba(0, 0, 0, .7);
  transform: translate3d(0, 0, 0);
}

.modal-content {
  position: absolute; top: 50%; left: 50%;
  transform: translate(-50%, -50%);
}

.modal-content > p {
  margin: 0;
  width: 400px;
  vertical-align: middle;
  text-align: center;
  font: bold 12px/100px sans-serif;
  letter-spacing: .1em;
  color: #aaa;
  background: #fff;
}
</style>
