<style>
.breaking-news {
  background-color: #33A3F1;
  color: #ffffff;
  border-radius: 10px 50px 50px 10px;
  padding: 5px;
}

.media-content {
  padding: 5px;
}

.time {
  color: #33A3F1;
}

.news {
  color: #666666;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 1s
}
.fade-enter, .fade-leave-to {
  opacity: 0
}
.breaking-news{
  background-color: #ff5722;
}
</style>

<template>
  <v-container fluid>
    <v-row>
      <v-col cols="12">
        <div
          id="app"
          class="ticker box"
        >
          <article class="media">
            <span class="breaking-news media-left">공지</span>
            <div class="media-content d-inline-block">
              <span class="time mr-2">11:36</span>
              <transition
                name="fade"
                tag="div"
                mode="out-in"
              >
                <a
                  v-if="news[0]"
                  key="0"
                  class="news"
                  href="#"
                >오늘 자정부터 서버 점검 실시</a>
                <a
                  v-if="news[1]"
                  key="1"
                  class="news"
                  href="#"
                >굿즈 어드민 만족도 조사</a>
                <a
                  v-if="news[2]"
                  key="2"
                  class="news"
                  href="#"
                >위워크 컨퍼런스룸 예약 프로세스 및 확인사항 공지</a>
              </transition>
            </div>
          </article>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
const exhale = ms =>
  new Promise(resolve => setTimeout(resolve, ms))

export default {
  el: '#app',
  data: ()=> ({
    tickerLocation: 0,
    news: [
      true,
      false,
      false,
    ]
  }),
  created: function() {
    setInterval(this.updateTicker, 5000);
  },
  methods: {
    updateTicker: function() {
      var removed = this.news.pop();
      this.news.unshift(removed);
    }
  }
}
</script>

<style scoped>

</style>