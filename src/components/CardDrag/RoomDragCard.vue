<template>
  <div id="cardDrag" @mousedown="dragCardFunction" class="cardIsDown">
    <div class="bgwhite">
      <div id="mydivheader" style="cursor: pointer">
        <svg
          width="875"
          height="5"
          viewBox="0 0 875 50"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <rect x="0.5" y="0.5" width="874" height="49" rx="4" fill="#F2F2F2" stroke="#BFBFBF" />
          <rect x="21" y="19" width="833" height="1" fill="#BFBFBF" />
          <rect x="21" y="29" width="833" height="1" fill="#BFBFBF" />
          <rect x="21" y="39" width="833" height="1" fill="#BFBFBF" />
        </svg>
      </div>

      <div class="card-head bgwhite">
        <h1>CB-KOM 5</h1>
        <span>Fakultas Sekolah Vokasi - Gedung CB Lantai 2</span>
      </div>
      <div class="card-body bgwhite">
        <h2>Foto Ruangan</h2>
        <swiper
          :slides-per-view="2"
          :space-between="5"
          @swiper="onSwiper"
          @slideChange="onSlideChange"
        >
          <swiper-slide>
            <PhotoSliderCard />
          </swiper-slide>
          <swiper-slide>
            <PhotoSliderCard />
          </swiper-slide>
          <swiper-slide>
            <PhotoSliderCard />
          </swiper-slide>
          <swiper-slide>
            <PhotoSliderCard />
          </swiper-slide>
          <swiper-slide>
            <PhotoSliderCard />
          </swiper-slide>
        </swiper>
        <div class="text-box">
        <h2>Keterangan Ruangan</h2>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. 
          Commodi eius id earum accusantium at nulla dolorum fugiat velit optio ullam. 
          Nulla culpa nihil sed dignissimos omnis eos sapiente et earum.</p>
        </div>
      </div>
      <div class="card-footer bgwhite">Tampilkan Lagi</div>
    </div>
  </div>
</template>
<script setup>
import PhotoSliderCard from '../CardSlider/PhotoSliderCard.vue'
</script>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'

// Import Swiper styles
import 'swiper/css'

export default {
  data() {
    return {
      isDown: false,
      heightPosition: 25
    }
  },
  components: {
    Swiper,
    SwiperSlide
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper)
    }
    const onSlideChange = () => {
      console.log('slide change')
    }
    return {
      onSwiper,
      onSlideChange
    }
  },
  mounted() {
    this.elmnt = this.$el.querySelector('.cardDrag')
  },
  methods: {
    dragCardFunction(e) {
      e.preventDefault()
      this.heightPosition = 55
      if (this.isDown) {
        document.getElementById('cardDrag').className = 'cardIsUp'
      } else {
        document.getElementById('cardDrag').className = 'cardIsDown'
      }
      this.isDown = !this.isDown
    }
  }
}
</script>
<style scoped>
.bgwhite{
  background-color: white;
}

#cardDrag {
  width: 100% !important;
  background-color: white;
  position: absolute;
  bottom: 0;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
  animation: 4s ease-in-out 0s 1 animationShow;
}

@keyframes animationShow {
    0% {
        height: 55%;

    }
    100% {
        height: 25%;
    }
}

#mydivheader {
  display: flex;
  justify-content: center;
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: white;
}

.card-head {
  padding-left: 10px;
  padding-right: 10px;
  background-color: white;
}

.card-body {
  padding-left: 10px;
  padding-right: 10px;
  background-color: white;
}

.card-footer {
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 30px;
  display: flex;
  justify-content: center;
  justify-items: center;
  background-color: white;
}

h1 {
  font-size: x-large;
  margin-bottom: 4px;
}

h2 {
  font-size: larger;
}

.cardIsDown {
  height: 25% !important;
  transition: height 1s;
}

.cardIsUp {
  height: 55% !important;
  transition: height 1s;
}
</style>
