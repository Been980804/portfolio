<template>
  <div class="popup_container" @click="closeIfOutsidePopup">
    <div class="popup_main" @click.stop>
      <div class="close_popup" @click="close_portfolio">
        <img src="../../assets/img/close-window.png" class="close_img" />
      </div>
      <div class="popup_body">
        <img src="../../assets/img/project/portfolio.png" class="popup_img" />
        <div class="popup_info">
          <strong>도서관 대여/예약 서비스</strong>

          <ul class="popup_info_list">
            <li><strong>Description</strong></li>
            <div class="popup_info_contents">
              <ul>
                <li>저의 포트폴리오입니다. Vue.js를 통해 구성하였습니다.</li>
                <li>인원 : 1인 프로젝트</li>
                <li>개발 파트 : 프론트엔드(Vue.js)</li>
                <li>개발 기간 : 1주</li>
              </ul>
            </div>
            <br>
            <div class="goDetail" @click="openDetail">Go Detail...</div>
          </ul>
          <ul class="popup_info_list">
            <li><strong>Skill</strong></li>
            <div class="popup_info_contents">
              <ul class="popup_skill_list">
                <li>JavaScript</li>
                <li>Vue.js</li>
                <li>vue-router</li>
              </ul>
            </div>
          </ul>
          <ul class="popup_info_list">
            <li><strong>GitHub</strong></li>
            <div class="popup_info_contents">
              <a href="https://github.com/Been980804/Portfolio"
                >https://github.com/Been980804/Portfolio</a
              >   
            </div>
          </ul>
        </div>
      </div>
    </div>
    <PortfolioDetailP v-if="showDetail" @close="closeDetail"/>
  </div>
</template>

<script>
import PortfolioDetailP from './PortfolioDetailP.vue';

export default {
  components: {
    PortfolioDetailP,
  },
  data(){
    return{
      showDetail : false,
    }
  },
  methods: {
    close_portfolio() {
      this.$emit("close");
    },
    closeIfOutsidePopup(event) {
      if (event.target === event.currentTarget) {
        this.close_portfolio();
      }
    },
    openDetail(){
      this.showDetail = true;
    },
    closeDetail(){
      this.showDetail = false;
    }
  },
};
</script>

<style>
@import "../../assets/css/popup.css";
</style>
