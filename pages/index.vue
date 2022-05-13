
<template>
  <div class="container">
    <div style="display: none">
      <!-- example start -->

      <!-- basic tags -->
      <div></div>
      <span></span>

      <!-- text -->
      <em></em>
      <strong></strong>

      <!-- actions -->
      <button></button>
      <a href="/"></a>

      <!-- layout -->
      <header></header>
      <main>
        <!-- h1, h2, h3, h4, h5 -->
        <h1></h1>
        <h2></h2>
        <section></section>
        <article></article>
      </main>
      <nav></nav>
      <footer></footer>

      <!-- assets -->
      <img src="/image.png" width="100px" height="100px" />
      <audio src="/audio.mp3" />
      <video src="/video.mp4" />
      <!-- example end -->
    </div>
    <header class="header">VIP</header>
    <body class="body">
      <div class="banner banner--lg">
        <div class="banner__icon banner__icon--1"></div>
        <h2 class="banner__title banner__title--main">普通会员</h2>
        <h5 class="banner__subtitle banner__subtitle--main">
          每日可领取3次任务
        </h5>
        <p class="banner__text banner__text--main">2020.08.11止</p>
      </div>
      <div
        class="banner banner--md banner--md1"
        @click="handleToggleDetail('silver', true)"
      >
        <div class="banner__left">
          <h2 class="banner__title">白银会员</h2>
          <h5 class="banner__subtitle" v-show="toggleDetail['silver']">
            每日可领取10次任务
          </h5>
          <p class="banner__text" v-show="toggleDetail['silver']">
            [1.20元/条]
          </p>
        </div>
        <div class="banner__right">
          <div
            class="banner__money"
            :class="{ 'banner__money--spacedSmall': !toggleDetail['silver'] }"
          >
            ￥330.00
          </div>
          <button
            class="btn btn--primary"
            v-show="toggleDetail['silver']"
            @click="toggleDialog = true"
          >
            立即加入
          </button>
        </div>
      </div>
      <div
        class="banner banner--md banner--md2"
        @click="handleToggleDetail('gold', true)"
      >
        <div class="banner__left">
          <h2 class="banner__title">黄金会员</h2>
          <h5 class="banner__subtitle">每日可领取19次任务</h5>
        </div>
        <div class="banner__right">
          <div
            class="banner__money"
            :class="{ 'banner__money--spaced': !toggleDetail['gold'] }"
          >
            ￥660.00
          </div>
          <button
            class="btn btn--primary"
            v-show="toggleDetail['gold']"
            @click="toggleDialog = true"
          >
            立即加入
          </button>
        </div>
      </div>
      <div
        class="banner banner--md banner--md3"
        @click="handleToggleDetail('plat', true)"
      >
        <div class="banner__left">
          <h2 class="banner__title">铂金会员</h2>
          <h5 class="banner__subtitle">每日可领取28次任务</h5>
        </div>
        <div class="banner__right">
          <div
            class="banner__money"
            :class="{ 'banner__money--spaced': !toggleDetail['plat'] }"
          >
            ￥990.00
          </div>
          <button
            class="btn btn--primary"
            v-show="toggleDetail['plat']"
            @click="toggleDialog = true"
          >
            立即加入
          </button>
        </div>
      </div>
      <div
        class="banner banner--md banner--md4"
        @click="handleToggleDetail('dia', true)"
      >
        <div class="banner__left">
          <h2 class="banner__title">钻石会员</h2>
          <h5 class="banner__subtitle">每日可领取99次任务</h5>
        </div>
        <div class="banner__right">
          <div
            class="banner__money"
            :class="{ 'banner__money--spaced': !toggleDetail['dia'] }"
          >
            ￥2990.00
          </div>
          <button
            class="btn btn--primary"
            v-show="toggleDetail['dia']"
            @click="toggleDialog = true"
          >
            立即加入
          </button>
        </div>
      </div>
      <div
        class="banner banner--md banner--md5"
        @click="handleToggleDetail('vip', true)"
      >
        <div class="banner__left">
          <h2 class="banner__title">荣耀会员</h2>
          <h5 class="banner__subtitle">每日可领取228次任务</h5>
        </div>
        <div class="banner__right">
          <div
            class="banner__money"
            :class="{ 'banner__money--spaced': !toggleDetail['vip'] }"
          >
            ￥5940.00
          </div>
          <button
            class="btn btn--primary"
            v-show="toggleDetail['vip']"
            @click="toggleDialog = true"
          >
            立即加入
          </button>
        </div>
      </div>
      <div
        class="banner banner--md banner--md6"
        @click="handleToggleDetail('vvip', true)"
      >
        <div class="banner__left">
          <h2 class="banner__title">尊耀会员</h2>
          <h5 class="banner__subtitle">每日可领取338次任务</h5>
        </div>
        <div class="banner__right">
          <div
            class="banner__money"
            :class="{ 'banner__money--spaced': !toggleDetail['vvip'] }"
          >
            ￥9899.00
          </div>
          <button
            class="btn btn--primary"
            v-show="toggleDetail['vvip']"
            @click="toggleDialog = true"
          >
            立即加入
          </button>
        </div>
      </div>
    </body>
    <footer class="footer">
      <div class="footerItem">
        <div class="footerItem__icon footerItem__icon--1"></div>
        <div class="footerItem__text">任務</div>
      </div>
      <div class="footerItem">
        <div class="footerItem__icon footerItem__icon--2"></div>
        <div class="footerItem__text">任務</div>
      </div>
      <div class="footerItem">
        <div class="footerItem__icon footerItem__icon--3"></div>
        <div class="footerItem__text">VIP</div>
      </div>
      <div class="footerItem">
        <div class="footerItem__icon footerItem__icon--4"></div>
        <div class="footerItem__text">我的</div>
      </div>
    </footer>
    <button class="floatingBtn">
      <div class="floatingBtn__icon"></div>
    </button>
    <div class="mask" v-show="toggleDialog"></div>
    <div class="dialog" v-show="toggleDialog">
      <div class="dialog__title">提示</div>
      <p class="dialog__text">
        確定花費{{ price }}元 <br />
        成為12個月的{{ membershipType }}會員嗎?
      </p>
      <div class="dialog__btnBox">
        <button
          class="btn btn--secondary btn--fat"
          @click="toggleDialog = false"
        >
          取消
        </button>
        <button
          class="btn btn--conseq btn--primary2 btn--fat"
          @click="toggleDialog = false"
        >
          确定
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      toggleDialog: false,
      toggleDetail: {
        silver: false,
        gold: false,
        plat: false,
        dia: false,
        vip: false,
        vvip: false,
      },
    };
  },
  computed: {
    price() {
      const priceMap = {
        silver: 330,
        gold: 660,
        plat: 990,
        dia: 2990,
        vip: 5940,
        vvip: 9899,
      };
      const activeItem = Object.keys(this.toggleDetail).find(
        (item) => this.toggleDetail[item]
      );
      if (activeItem) {
        return priceMap[activeItem];
      } else {
        return 0;
      }
    },
    membershipType() {
      const membershipMap = {
        silver: "白銀",
        gold: "黃金",
        plat: "柏金",
        dia: "鑽石",
        vip: "榮耀",
        vvip: "尊耀",
      };
      const activeItem = Object.keys(this.toggleDetail).find(
        (item) => this.toggleDetail[item]
      );
      if (activeItem) {
        return membershipMap[activeItem];
      } else {
        return "";
      }
    },
  },
  methods: {
    handleToggleDetail(type, action) {
      Object.keys(this.toggleDetail).forEach((item) => {
        this.toggleDetail[item] = false;
      });
      this.toggleDetail[type] = action;
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  border-radius: 40px;
  padding: 10px 18px;
  outline: none;
  border: none;
  font-size: 16px;
  cursor: pointer;
  &--primary {
    color: #8a56ac;
    background-color: #fff;
  }
  &--primary2 {
    background-color: #8a56ac;
    color: #fff;
  }
  &--secondary {
    background-color: #9599b3;
    color: #fff;
  }
  &--conseq {
    margin-left: 12px;
  }
  &--fat {
    padding-left: 31px;
    padding-right: 31px;
    padding-top: 12px;
    padding-bottom: 12px;
  }
}
.floatingBtn {
  position: absolute;
  bottom: calc(44px + 64px);
  right: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 52px;
  height: 52px;
  border-radius: 50%;
  border: none;
  outline: none;
  background-color: #8a56ac;
  cursor: pointer;
  &__icon {
    width: 30px;
    height: 30px;
    background-size: contain;
    background-position: center center;
    background-repeat: no-repeat;
    background-image: url(/4.svg);
  }
}
.mask {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 4;
  background-color: #000000cc;
}
.dialog {
  min-width: 327px;
  position: absolute;
  top: 220px;
  left: 50%;
  z-index: 5;
  transform: translate(-50%, 0);
  border-top-right-radius: 8px;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 65px;
  background-color: #fff;
  padding-left: 32px;
  padding-top: 24px;
  padding-bottom: 24px;
  padding-right: 24px;
  transition: opacity 0.3s;
  &__title {
    font-size: 26px;
    color: #000;
    font-weight: bold;
  }
  &__text {
    font-size: 14px;
    color: #998fa2;
    margin-top: 10px;
    margin-bottom: 28px;
  }
  &__btnBox {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
}

.container {
  width: 100vw;
  overflow-x: hidden;
}
.header {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 44px;
  background-color: #fff;
  color: #000;
  font-size: 1rem;
}
.body {
  width: 100vw;
  height: calc(100vh - 44px - 64px);
  overflow: auto;
}
.banner {
  border-bottom-left-radius: 65px;
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  &--lg {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 183px;
    width: 100vw;
    background-color: rgba(138, 86, 172, 1);
    background-image: url(/bg1.png);
  }
  &--md {
    position: relative;
    display: flex;
    padding-left: 56px;
    padding-right: 22px;
    padding-top: 33px;
    padding-bottom: 33px;
    &:before {
      content: "";
      display: block;
      width: 60px;
      height: 60px;
      position: absolute;
      top: -60px;
      left: 0;
      z-index: -1;
    }
  }
  &--md1,
  &--md3,
  &--md5 {
    &:before {
      background-color: #352641;
    }
  }
  &--md2,
  &--md4,
  &--md6 {
    &:before {
      background-color: #241332;
    }
  }
  &--md1 {
    background-color: #352641;
    background-image: url(/bg2.png);
  }
  &--md2 {
    background-color: #241332;
    background-image: url(/bg3.png);
  }
  &--md3 {
    background-color: #352641;
    background-image: url(/bg4.png);
  }
  &--md4 {
    background-color: #241332;
    background-image: url(/bg6.png);
  }
  &--md5 {
    background-color: #352641;
    background-image: url(/bg5.png);
  }
  &--md6 {
    background-color: #241332;
    background-image: url(/bg7.png);
  }
  &__right {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    margin-left: auto;
  }
  &__money {
    margin-right: 9px;
    margin-bottom: 11px;
    color: #fff;
    font-weight: bold;
    font-size: 20px;
    color: rgba(255, 255, 255, 0.6);
    &--spaced {
      margin-top: 33px;
    }
    &--spacedSmall {
      margin-top: 6px;
    }
  }
  &__icon,
  &__title,
  &__subtitle,
  &__text {
    color: rgba(255, 255, 255, 0.6);
    &--main {
      color: #fff;
    }
  }
  &__icon,
  &__title,
  &__subtitle {
    margin-bottom: 4px;
  }
  &__subtitle,
  &__text {
    opacity: 0.72;
    font-weight: 100;
  }
  &__icon {
    width: 60px;
    height: 60px;
    background-size: contain;
    background-position: center center;
    background-repeat: no-repeat;
    background-image: url(/ic1.svg);
  }
  &__title {
    font-size: 26px;
    font-weight: bold;
  }
  &__subtitle {
    font-size: 14px;
    font-weight: 100;
  }
  &__text {
    font-size: 1rem;
  }
}
.footer {
  position: absolute;
  bottom: 0;
  left: 0;
  display: flex;
  width: 100vw;
  height: 64px;
  background-color: #fff;
  color: #717171;
}
.footerItem {
  flex: 0 0 25%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  &__icon {
    width: 22px;
    height: 20px;
    background-size: contain;
    background-position: center center;
    background-repeat: no-repeat;
    margin-bottom: 8px;
    &--1 {
      background-image: url(/2.svg);
    }
    &--2 {
      background-image: url(/3.svg);
    }
    &--3 {
      background-image: url(/1.svg);
    }
    &--4 {
      background-image: url(/3.svg);
    }
  }
  &__text {
    color: #717171;
  }
}
</style>
