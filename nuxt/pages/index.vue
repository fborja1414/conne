<template>
  <div class="body">
    <aside class="content">
      <div class="logo">
        <img class="image" src="~assets/logo.png" />
      </div>
      <div class="image-container">
        <img class="pic1" src="@/assets/PIC.png" draggable="false" />
        <img class="pic2" src="@/assets/PIC3.png" draggable="false" />
        <img class="pic3" src="@/assets/PIC2.png" draggable="false" />
        <div class="extra-space"></div>
      </div>
    </aside>
    <div class="header neue-light" id="header">
      <ul class="nav">
        <li>HOME</li>
        <li>ABOUT</li>
        <li>SHOP</li>
        <li>CART({{ cart }})</li>
      </ul>
      <div class="toggle-font">
        Font Size:
        <div
          class="f"
          @click="
            eighteen = false;
            twentysix = false;
          "
        >
          12px
        </div>
        <div
          class="f"
          @click="
            eighteen = true;
            twentysix = false;
          "
        >
          18px
        </div>
        <div class="f" @click="twentysix = true">26px</div>
      </div>
      <div class="toggle-container">
        <div class="toggle" @click="toggle3D()">
          Toggle 3D:
          <div v-if="dimensiontoggle">OFF</div>
          <div v-if="!dimensiontoggle">ON</div>
        </div>
      </div>
      <div
        class="description-container"
        :class="{
          eighteen: eighteen,
          twentysix: twentysix,
          forcewidth: twentysix,
        }"
      >
        <div
          class="title neue-light"
          :class="{ eighteen: eighteen, twentysix: twentysix }"
        >
          THE DABY
        </div>
        <div class="price neue">$68 USD</div>
        <div class="description neue">
          Launching the Daby in a beautiful neon green so that we can inject
          some more cool into your life. This model is wearing a size large for
          37" chest, 30.5" waist and 40.5" hips. Refer to the size guide for
          more info.<br /><br />Made of 95% acetate, 5% spandex for a stretchy
          fit. Sustainably made using advances in AI throughout production
          pipeline.
        </div>
      </div>
      <div
        class="size-container"
        :class="{ eighteen: eighteen, twentysix: twentysix }"
      >
        <div class="container">
          <div class="sizing neue">Select Size</div>
          <div class="guide neue">Size Guide</div>
        </div>
        <div
          class="drop-down neue-light"
          :class="{ eighteen: eighteen, twentysix: twentysix }"
        >
          <div
            class="s"
            :class="{ active: xsmall }"
            @click="
              xsmall = true;
              small = false;
              medium = false;
              large = false;
              xlarge = false;
            "
          >
            X-Small
          </div>
          <div
            class="s"
            :class="{ active: small }"
            @click="
              xsmall = false;
              small = true;
              medium = false;
              large = false;
              xlarge = false;
            "
          >
            Small
          </div>
          <div
            class="s"
            :class="{ active: medium }"
            @click="
              xsmall = false;
              small = false;
              medium = true;
              large = false;
              xlarge = false;
            "
          >
            Medium
          </div>
          <div
            class="s"
            :class="{ active: large }"
            @click="
              xsmall = false;
              small = false;
              medium = false;
              large = true;
              xlarge = false;
            "
          >
            Large
          </div>
          <div
            class="s l"
            :class="{ active: xlarge }"
            @click="
              xsmall = false;
              small = false;
              medium = false;
              large = false;
              xlarge = true;
            "
          >
            X-Large
          </div>
        </div>
        <div class="buy-button" @click="updateCart">
          <div
            class="cart-text neue-light"
            :class="{ eighteen: eighteen, twentysix: twentysix }"
            v-if="!carttext"
          >
            ADD TO CART
          </div>
          <div
            class="updated neue-light"
            :class="{ eighteen: eighteen, twentysix: twentysix }"
            v-if="carttext"
          >
            ADDED
          </div>
        </div>
        <div
          class="shipping neue"
          :class="{ eighteen: eighteen, twentysix: twentysix }"
        >
          Shipping &amp; Returns
        </div>
        <div
          class="info neue"
          :class="{ eighteen: eighteen, twentysix: twentysix }"
        >
          How are we sustainable?
        </div>
      </div>
      <Matter v-show="!dimensiontoggle" />

      <div class="footer">
        <div class="footer-images">
          <div class="space-container">
            <div class="space"></div>
            <img class="firstfooter" src="@/assets/sd.png" />
          </div>
          <img src="@/assets/qwq.png" />
          <img src="@/assets/jkjk.png" />
        </div>
      </div>
    </div>

    <list
      class="list"
      :cart="cart"
      :small="small"
      :xsmall="xsmall"
      :medium="medium"
      :large="large"
      :xlarge="xlarge"
    />
  </div>
</template>

<script>
import Matter from "@/components/Matter.vue";
import List from "@/components/List.vue";

export default {
  name: "index",
  components: {
    Matter,
    List,
  },

  methods: {
    updateCart() {
      this.cart++;
      this.carttext = true;
      setTimeout(() => {
        this.carttext = false;
      }, 500);
    },

    toggle3D() {
      if (this.dimensiontoggle == true) {
        this.dimensiontoggle = false;
        console.log("false");
      } else {
        this.dimensiontoggle = true;
        console.log("true");
      }
    },

    // },
    // waitToggle() {
    //   setTimeout(() => {
    //     this.togglebutton = true;
    //   }, 20 * 1000);
    // },
  },

  mounted() {
    // this.waitToggle();
  },

  data() {
    return {
      cart: 0,
      xsmall: false,
      small: false,
      medium: false,
      large: false,
      xlarge: false,
      dimensiontoggle: false,
      togglebutton: false,
      carttext: false,
      eighteen: false,
      twentysix: false,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "~assets/_typography.scss";
.body {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
}

.header {
  //position: relative;
  //display: flex;
  z-index: 4;
  font-size: 1rem;
  //justify-content: flex-end;
  width: 50%;
  // height: 100vh;
  // overflow-y: scroll;
  // display: block;
  // pointer-events: auto;
}

.content {
  width: 50%;
  border-right: solid 1px black;
  // height: 100vh;
  // overflow: scroll;
  display: block;
  //padding: 2rem;
}

.logo {
  position: sticky;
  top: 0px;
  display: flex;
  padding: 2rem 0;
  z-index: 5 !important;
  pointer-events: auto;
  cursor: pointer;
  .image {
    max-width: 25vw;
    z-index: 100 !important;
    pointer-events: auto;
  }
}

.nav {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  list-style: none;
  padding: 1rem;
  padding-bottom: 4rem;
  position: sticky;
  top: 0px;
  mix-blend-mode: color-dodge;
  //background: white;
}

// .toggle-container {
//   display: flex;
// }
.toggle {
  display: flex;
  position: fixed;
  right: 10px;
  bottom: 10px;
  // margin-left: 7rem;
  z-index: 5 !important;
  cursor: pointer;
}

li {
  padding: 1rem;
  cursor: pointer;
  pointer-events: auto;
  z-index: 5 !important;
}

.image-container {
  position: relative;
  max-width: 50vw;
  border: none;

  //justify-content: flex-start;
  img {
    width: 100%;
    margin-bottom: 5rem;
    z-index: -1;
  }
  img:nth-child(3) {
    margin: 0;
  }
}

.description-container {
  display: grid;
  padding-top: 3rem;
  grid-template-columns: 30vw;
  justify-content: center;
  font-size: 12px;
}

.neue {
  @include neue;
}

.neue-light {
  @include neue-light;
}

.title {
  font-size: 15px;
  font-weight: bold;
}

.price {
  margin-bottom: 2rem;
}

.size-container {
  display: grid;
  margin: 4rem;
  margin-bottom: 50rem;
  justify-content: center;
  //align-items: center;
  z-index: 100;
}

.sizing {
  padding-bottom: 1rem;
}
.drop-down {
  display: grid;
  grid-template-columns: repeat(5, 6vw);
  padding-bottom: 2rem;
  font-size: 12px;
  z-index: 5 !important;
  @media only screen and (max-width: 1200px) {
    border: none;
    width: 30vw;
    display: block;
    font-size: 12px;
    padding-bottom: 1rem;
  }
}

.toggle-on {
  opacity: 1;
}

.s {
  padding: 10px;
  border-top: solid 2px black;
  border-right: solid 2px black;
  border-bottom: solid 2px black;
  overflow: hidden;
  @media only screen and (max-width: 1200px) {
    border: none;
    padding: 0px;
  }
}

.l {
  border-right: none;
  overflow: hidden;
}

.s:hover {
  font-weight: bold;
  cursor: pointer;
}

.active {
  font-weight: bold;
  cursor: pointer;
}

.pic1,
.pic2,
.pic3 {
  border-top: 1px solid black;

  border-bottom: 1px solid black;

  border-left: 1px solid black;
}

.container {
  display: flex;
  justify-content: space-between;
  line-height: 0.5em;
  font-size: 12px;
}

.guide {
  font-size: 12px;
  cursor: pointer;
}

.buy-button {
  display: flex;
  justify-content: center;
  padding: 10px;
  border: solid 1px black;
  width: 10rem;
  cursor: pointer;
  background-color: #adff2f;
  z-index: 5 !important;
}

.cart-text {
  font-size: 12px;
}

.updated {
  font-size: 12px;
}
.shipping {
  padding-top: 3rem;
  padding-bottom: 10px;
  pointer-events: auto;
  //margin-left: 7rem;
  width: 12rem;
  font-size: 12px;
  cursor: pointer;
  z-index: 5 !important;
}

.info {
  padding-top: 10px;
  padding-bottom: 10px;
  //margin-left: 7rem;
  width: 13rem;
  font-size: 12px;
  cursor: pointer;
  pointer-events: auto;
  z-index: 5 !important;
}
.footer {
  // max-width: 51vw;
  position: absolute;
  // //right: 55px;
  bottom: 0px;
  //background: white;
  //z-index: 100;
}

.footer-images {
  display: grid;
  grid-template-columns: repeat(3, 15vw);

  img {
    width: 100%;
    border-top: 1px solid black;
  }
  img:nth-child(3) {
    border-right: none;
    border-left: 1px solid black;
  }
  img:nth-child(1) {
    border: none;
  }
}
.space {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  border-top: 1px solid black;
  border-right: 1px solid black;
}

.space-container {
  position: relative;
}

.extra-space {
  margin: 0;
  padding: 0;
  height: 104px;
}

.firstfooter {
  padding-top: 10px;
}

.list {
  display: none;
  //opacity: 0;
}

.toggle-font {
  cursor: pointer;
  position: fixed;
  bottom: 10px;
  right: 150px;
  //font-size: 12px;
  display: flex;
  z-index: 5 !important;
  //align-items: flex-end;
  //justify-content: flex-end;
  //padding: 1rem;
  .f {
    padding-left: 10px;
  }
}

.eighteen {
  font-size: 18px;
  .title {
    font-size: 20px;
  }
  .guide {
    font-size: 15px;
  }
  .sizing {
    font-size: 15px;
  }
}

.twentysix {
  font-size: 26px;
  .drop-down {
    grid-template-columns: repeat(5, 8vw);
  }
  .shipping {
    width: 15rem;
  }
  .info {
    width: 20rem;
  }
  .buy-button {
    width: 15rem;
  }
  .title {
    font-size: 28px;
  }
  .guide {
    font-size: 18px;
  }
  .sizing {
    font-size: 18px;
  }
}

.forcewidth {
  display: grid;
  grid-template-columns: 40vw;
  padding: 3rem;
  @media only screen and (max-width: 1217px) {
    grid-template-columns: 30vw;
  }
}

//media queries tablet portrait
@media only screen and (max-width: 768px) {
  .list {
    opacity: 1;
    display: block;
    // display: none;
  }
  .content {
    display: none;
    z-index: 5 !important;
  }
  .header {
    display: none;
  }
}
</style>
