<template>
  <div class="body">
    <div class="content">
      <div class="logo">
        <img src="~assets/logo.png" />
      </div>
      <div class="image-container">
        <img class="pic1" src="@/assets/PIC.png" />
        <img class="pic2" src="@/assets/PIC2.png" />
        <img class="pic3" src="@/assets/PIC3.png" />
      </div>
    </div>
    <div class="header">
      <ul class="nav">
        <li>HOME</li>
        <li>ABOUT</li>
        <li>SHOP</li>
        <li>CART({{ cart }})</li>
      </ul>
      <div class="description-container">
        <div class="title">THE DABY</div>
        <div class="price">$68 USD</div>
        <div class="description">
          Launching the Daby in a beautiful neon green so that we can inject
          some more cool into your life. This model is wearing a size large for
          37" chest, 30.5" waist and 40.5" hips. Refer to the size guide for
          more info.<br /><br />Made of 95% acetate, 5% spandex for a stretchy
          fit. Sustainably made using advances in AI throughout production
          pipeline.
        </div>
      </div>
      <div class="size-container">
        <div class="container">
          <div class="sizing">Select Size</div>
          <div class="guide">Size Guide</div>
        </div>
        <div class="drop-down">
          <div class="s" :class="{ active: xsmall }" @click="size('xsmall')">
            X-Small
          </div>
          <div class="s" :class="{ active: small }" @click="size('small')">
            Small
          </div>
          <div class="s" :class="{ active: medium }" @click="size('medium')">
            Medium
          </div>
          <div class="s" :class="{ active: large }" @click="size('large')">
            Large
          </div>
          <div class="s l" :class="{ active: xlarge }" @click="size('xlarge')">
            X-Large
          </div>
        </div>
      </div>
      <div class="buy-button" @click="updateCart">
        <div class="cart-text">
          ADD TO CART
        </div>
      </div>
      <div class="shipping">Shipping &amp; Returns</div>
      <div class="info">How are we sustainable?</div>
      <div class="footer">
        <div class="footer-images">
          <img src="@/assets/sd.png" />
          <img src="@/assets/qwq.png" />
          <img src="@/assets/jkjk.png" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",

  methods: {
    updateCart() {
      this.cart++;
    },

    size(item) {
      console.log("small");
      switch (item) {
        case "xsmall":
          if (
            this.xsmall == true ||
            this.small == true ||
            this.medium == true ||
            this.large == true ||
            this.xlarge == true
          )
            this.xsmall = false;
          else this.xsmall = true;

          break;
        case "small":
          if (
            this.xsmall == true ||
            this.small == true ||
            this.medium == true ||
            this.large == true ||
            this.xlarge == true
          )
            this.small = false;
          else this.small = true;
          break;
        case "medium":
          if (
            this.xsmall == true ||
            this.small == true ||
            this.medium == true ||
            this.large == true ||
            this.xlarge == true
          )
            this.medium = false;
          else this.medium = true;
          break;
        case "large":
          if (
            this.xsmall == true ||
            this.small == true ||
            this.medium == true ||
            this.large == true ||
            this.xlarge == true
          )
            this.large = false;
          else this.large = true;
          break;
        case "xlarge":
          if (
            this.xsmall == true ||
            this.small == true ||
            this.medium == true ||
            this.large == true ||
            this.xlarge == true
          )
            this.xlarge = false;
          else this.xlarge = true;
          break;
      }
    }
  },

  data() {
    return {
      cart: 0,
      xsmall: false,
      small: false,
      medium: false,
      large: false,
      xlarge: false
    };
  }
};
</script>

<style lang="scss" scoped>
@import "~assets/_typography.scss";
.body {
  display: flex;
  z-index: 3;
  margin: 0;
  padding: 0 55px;
}

.header {
  position: relative;
  //display: flex;
  z-index: 3;
  font-size: 1rem;
  justify-content: flex-end;
  width: 50vw;
}

.content {
  width: 50vw;
  border-right: solid 1px black;
}

.logo {
  display: block;
  padding: 2rem 0;
  img {
    max-width: 25vw;
  }
  cursor: pointer;
}

.nav {
  display: flex;
  justify-content: flex-end;
  list-style: none;
  padding: 1rem;
  padding-bottom: 4rem;
}

li {
  padding: 1rem;
  cursor: pointer;
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
}
.description-container {
  display: grid;
  padding-top: 5rem;
  grid-template-columns: 30vw;
  justify-content: center;
  font-size: 20px;
}

.title {
  font-size: 30px;
  font-weight: bold;
}

.price {
  margin-bottom: 4rem;
}

.size-container {
  display: grid;
  margin: 4rem;
  justify-content: center;
  //align-items: center;
}

.sizing {
  padding-bottom: 1rem;
}
.drop-down {
  display: grid;
  grid-template-columns: repeat(5, 6vw);
}

.s {
  padding: 10px;
  border-top: solid 2px black;
  border-right: solid 2px black;
  border-bottom: solid 2px black;
  overflow: hidden;
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

.container {
  display: flex;
  justify-content: space-between;
  line-height: 0.5em;
  font-size: 18px;
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
  margin-left: 7rem;
  cursor: pointer;
  background-color: #adff2f;
}

.shipping {
  padding-top: 3rem;
  padding-bottom: 10px;
  margin-left: 7rem;

  font-size: 18px;
  cursor: pointer;
}

.info {
  padding-top: 10px;
  padding-bottom: 10px;
  margin-left: 7rem;
  font-size: 18px;
  cursor: pointer;
}
.footer {
  position: absolute;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 1fr;
  grid-row: 1/2;
  bottom: 0;
  right: 0;
}
</style>
