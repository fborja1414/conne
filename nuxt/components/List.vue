<template>
  <div class="media-container">
    <div class="content-mediascreen">
      <div class="logo">
        <img class="image-mediascreen" src="~assets/logo.png" />
      </div>
      <div class="nav-container">
        <div class="nav neue-light">
          <div>HOME</div>
          <div>SHOP</div>
          <div>CART({{ cart }})</div>
        </div>
      </div>
    </div>
    <div class="images-container">
      <img class="pic1" src="@/assets/PIC.png" draggable="false" />
      <img class="pic2" src="@/assets/PIC3.png" draggable="false" />
      <img class="pic3" src="@/assets/PIC2.png" draggable="false" />
      <div class="extra-space"></div>
    </div>
    <div class="description-container">
      <div class="title neue-light">THE DABY</div>
      <div class="price neue-light">$68 USD</div>
    </div>
    <div class="description neue">
      Launching the Daby in a beautiful neon green so that we can inject some
      more cool into your life. This model is wearing a size large for 37"
      chest, 30.5" waist and 40.5" hips. Refer to the size guide for more
      info.<br /><br />Made of 95% acetate, 5% spandex for a stretchy fit.
      Sustainably made using advances in AI throughout production pipeline.
    </div>
    <div class="size-container">
      <div class="container">
        <div class="sizing neue">Select Size</div>
        <div class="guide neue">Size Guide</div>
      </div>
    </div>
    <div class="drop-down neue-light">
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
      <div class="cart-text neue-light" v-if="!carttext">ADD TO CART</div>
      <div class="updated neue-light" v-if="carttext">ADDED</div>
    </div>
    <div class="shipping neue">Shipping &amp; Returns</div>

    <div class="info neue">How are we sustainable?</div>

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
</template>

<script>
export default {
  name: "List",

  props: {
    cart: Number,
    xsmall: Boolean,
    small: Boolean,
    medium: Boolean,
    large: Boolean,
    xlarge: Boolean,
  },

  methods: {
    updateCart() {
      this.cart++;
      this.carttext = true;
      setTimeout(() => {
        this.carttext = false;
      }, 500);
    },
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
    };
  },
};
</script>

<style lang="scss" scoped>
@import "~assets/_typography.scss";

.content-mediascreen {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 2rem;
  margin-bottom: 2rem;
  position: sticky;
  top: 0rem;
  background: white;
}
.logo {
  //display: flex;

  width: 25vw;
  //justify-content: space between;
}

.image-mediascreen {
  width: 100%;
  justify-content: center;
}

.images-container {
  width: 80vw;
  //display: flex;
  // overflow-x: scroll;
}

.pic1,
.pic2,
.pic3 {
  width: 100%;
  margin-bottom: 4rem;
  border: solid 1px black;
}

.header-mediascreen {
  display: flex;
  justify-content: space-between;
}

.nav-container {
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
}
.nav {
  display: flex;
  list-style: none;
  //padding-top: 3rem;
  //padding-bottom: 4rem;
  cursor: pointer;
  align-items: center;
  align-content: center;
  div {
    display: flex;
    padding: 1rem;
    align-items: center;
    align-content: center;
  }
}

.media-container {
  //border-right: 1px solid black;
}

.description-container {
  display: grid;
  //padding-top: 5rem;
  grid-template-columns: 40vw 40vw;
  //justify-content: center;
  font-size: 20px;
  margin-bottom: 2rem;
}

.neue {
  @include neue;
}

.title {
  font-size: 30px;
  font-weight: bold;
}

.price {
  //padding-left: 10px;
  font-size: 30px;
  display: flex;
  justify-content: flex-end;
  //display: flex;
  //margin-bottom: 4rem;
}

.neue-light {
  @include neue-light;
}

.description {
  font-size: 20px;
  padding-bottom: 2rem;
  width: 80vw;
}
.size-container {
  margin-top: 2rem;
  // display: grid;
  //margin: 1rem;
  //justify-content: center;
  //align-items: center;
  z-index: 100;
}

.sizing {
  padding-bottom: 1rem;
}

.guide {
  padding-left: 20px;
  font-size: 15px;
  cursor: pointer;
}
.drop-down {
  display: grid;
  // grid-template-columns: repeat(5, 25vw);
  //padding-bottom: 2rem;
  font-size: 18px;
  padding-bottom: 2rem;
  z-index: 5 !important;
}
.container {
  display: flex;
  justify-content: space-between;
  line-height: 0.5em;
  font-size: 18px;
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

.shipping {
  padding-top: 3rem;
  padding-bottom: 10px;
  pointer-events: auto;
  //margin-left: 7rem;
  width: 12rem;
  font-size: 18px;
  cursor: pointer;
  z-index: 5 !important;
}

.info {
  padding-top: 10px;
  padding-bottom: 20rem;
  //margin-left: 7rem;
  width: 13rem;
  font-size: 18px;
  cursor: pointer;
  pointer-events: auto;
  z-index: 5 !important;
}
.footer {
  max-width: 100vw;
  position: absolute;
  left: 0px;
  //right: 55px;
  bottom: 0px;
}

.footer-images {
  //width: 100vw;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  //position: absolute;
  //left: 0px;

  img {
    width: 100%;
    border-top: 1px solid black;
  }
  img:nth-child(3) {
    border-right: none;
    // border-left: 1px solid black;
  }
  img:nth-child(1) {
    //border: 1px solid black;
  }
}

.media-container {
  position: relative;
}

.s:hover {
  font-weight: bold;
  cursor: pointer;
}

.active {
  font-weight: bold;
  cursor: pointer;
}
</style>