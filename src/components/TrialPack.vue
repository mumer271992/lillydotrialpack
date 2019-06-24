<template>
  <div class="trial-pack-page">
    <section id="banner_section">
      <div class="container f-h">
        <div class="banner_section_content">
          <div class="t-c">
            <h1 class="t-c">Discover our skin friendliness</h1>
            <button>Now choose your size</button>
          </div>
        </div>
      </div>
    </section>
    <section id="order_section">
      <div class="container">
        <div class="resp-flex-row justify-space-between">
          <div class="item order-image">
            <img :src="currentImage" />
          </div>
          <div class="item cart-section">
            <h2>Our free test package</h2>
            <div>CHOOSE YOUR SIZE</div>
            <div class="sizes">
              <div
                v-for="size of sizes"
                :key="size.number"
                @click="onSelect(size)"
                :class="`size-button ${size.number === selectedSize ? ' active' : ''}`"
              >
                <div>{{ size.number }}</div>
                <div>{{ size.weight }}</div>
              </div>
            </div>
            <div>Test our diapers and wipes now - In size 1 - 3 our test package contains our wipes with 99% water, from Gr. 4 you will receive our Sensitive Wet Wipes. We pay the products, you only the shipping.</div>
            <ul>
              <li>Automatic transition to the ever-terminable diaper subscription for € 49.50 per delivery.</li>
              <li>Prices include VAT, plus shipping costs</li>
            </ul>
            <button class="add-to-cart">Add To Cart</button>
          </div>
        </div>
      </div>
    </section>
    <section id="how_it_works">
      <div class="container t-c">
        <h2 class="t-c">How it works</h2>
        <div class="resp-flex-row justify-space-between m-b">
          <div class="item t-c">
            <div>
              <img src="../assets/images/lillydoo-your-trialbox-icon.svg" />
            </div>
            <h4>YOUR TEST PACKAGE</h4>
            <div>We give you the products, you take over only the postage.</div>
          </div>
          <div class="item t-c">
            <div>
              <img src="../assets/images/lillydoo-your-flexibility-icon.svg" />
            </div>
            <h4>YOUR FLEXIBILITY</h4>
            <div>First month box after 14 days for 49,50 € received. Or cancel before the first delivery.</div>
            <div class="links">
              <div><a href="#">Learn more about the</a></div>
              <div><a href="#">LILLYDOO diaper subscription here.</a></div>
            </div>
          </div>
          <div class="item t-c">
            <div>
              <img src="../assets/images/lillydoo-your-subscription-icon.svg" />
            </div>
            <h4>YOUR MONTHLY BOX</h4>
            <div>Adapt designs or delivery intervals at any time or change the diaper size.</div>
          </div>
        </div>
      </div>
    </section>
    <section id="package_details_section">
      <div class="container">
        <h2 class="t-c">Contains your test package</h2>
        <div class="resp-flex-row">
          <div class="item flex-row">
            <div>
              <img src="../assets/images/diaper.jpg" />
            </div>
            <div>
              <h4>10 LILLYDOO DIAPERS</h4>
              <ul>
                <li>0% perfumes & lotions, 100% LILLYDOO protection</li>
                <li>Extra soft and with an ideal fit</li>
              </ul>
            </div>
          </div>
          <div class="item flex-row">
            <div>
              <img src="../assets/images/water-wipes-15-small.jpg" />
            </div>
            <div>
              <h4>15 WET WIPES WITH 99% WATER</h4>
              <ul>
                <li>0% perfumes & PEGs, 100% biodegradable</li>
                <li>Naturally pure, extra mild, alternative to "water & cotton"</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import TestPacket1 from '../assets/images/lillydoo-testpaket-10.jpg';
import TestPacket2 from '../assets/images/lillydoo-testpaket-20.jpg';
import TestPacket3 from '../assets/images/lillydoo-testpaket-30.jpg';
import TestPacket4 from '../assets/images/lillydoo-testpaket-40.jpg';
import TestPacket5 from '../assets/images/lillydoo-testpaket-50.jpg';

export default {
  name: 'TrialPack',
  data() {
    return {
      currentImage: TestPacket1,
      selectedSize: 1,
      sizes: [
        {
          number: 1,
          weight: '2-3 KG',
          selected: false,
          image: TestPacket1,
        },
        {
          number: 2,
          weight: '2-3 KG',
          selected: false,
          image: TestPacket2,
        },
        {
          number: 3,
          weight: '2-3 KG',
          selected: false,
          image: TestPacket3,
        },
        {
          number: 4,
          weight: '2-3 KG',
          selected: false,
          image: TestPacket4,
        },
        {
          number: 5,
          weight: '2-3 KG',
          selected: false,
          image: TestPacket5,
        },
      ],
    };
  },
  methods: {
    onSelect(size) {
      this.selectedSize = size.number;
      this.currentImage = size.image;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.trial-pack-page {
  font-weight: 500;
  section {

  }
  h2{
    margin-bottom: 2rem;
  }
  #banner_section{
    position: relative;
    background-image: url('../assets/images/header-trialbox-tablet.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    height: 620px;
    .banner_section_content{
      display: flex;
      flex-direction: row;
      align-items: center;
      position: absolute;
      top: 50%;
      transform: translateY(-50%);

      >div:first-child {
        max-width: 19vw;
        @media(max-width: 1440px){
          max-width: 22vw;
          margin: auto;
        }
        @media(max-width: 1024px){
          max-width: 30vw;
          margin: auto;
        }
        @media(max-width: 768px){
          max-width: 40vw;
          margin: auto;
        }
        @media(max-width: 567px){
          max-width: 95vw;
          margin: auto;
        }
      }
      button{
        width: 100%;
      }
      @media(max-width: 567px) {
        top: 25%;
        transform: translateY(-25%);
      }
    }
  }
  #order_section {
    padding: 4rem 0;
    img {
      width: 100%;
    }
    ul {
      padding-inline-start: 20px;
    }
    button.add-to-cart {
      width: 100%;
      margin-top: 3rem;
    }
    .order-image{
      padding: 0 3rem;
    }
    .cart-section {
      padding: 0 3rem;
      h2{
        margin-top: 0;
      }
      .sizes{
        width: 100%;
        margin-top: 0.5rem;
        margin-bottom: 2rem;
        .size-button{
          cursor: pointer;
          display: inline-block;
          border: 1px solid #7c7c7c;
          text-align: center;
          padding: 7px 20px 2px 20px;
          color: #7c7c7c;
          margin-right: 10px;
          &:hover {
            color: #ffffff;
            background-color: #00afab;
            border-color: #00afab;
          }
          &.active{
            color: #ffffff;
            background-color: #00afab;
          }
          @media(max-width: 1024px) {
            padding: 10px 20px 5px 20px;
            margin-bottom: 10px;
          }
          @media(max-width: 768px) {
            padding: 10px 20px 5px 20px;
            margin-bottom: 10px;
          }
          @media(max-width: 567px) {
            padding: 10px 20px 5px 20px;
            margin-bottom: 10px;
          }
        }

      }
    }
    @media(max-width: 768px){
      .order-image, .cart-section {
        padding: 0 1rem;
      }
    }
    @media(max-width: 567px){
      .order-image, .cart-section {
        padding: 0;
      }
    }
  }
  #how_it_works {
    padding: 4rem 0;
    background-color: #f8f8f8;
    .item {
      padding: 0 1.5rem;
      @media(max-width: 567px){
        padding: 1.5rem 0;
      }
    }
    h2{
      margin-top: 0;
      margin-bottom: 2rem;
    }
    .links{
      margin-top: 2rem;
    }
  }
  #package_details_section {
    background-color: #ffffff;
    padding: 4rem 0;
    img {
      width: auto;
      height: 150px;
      margin-right: 1rem;
    }
    ul {
      padding-inline-start: 20px;
    }
    h4{
      margin-top: 0px;
    }
    @media(max-width: 1024px){
      .flex-row{
        >div{
          &:first-child{
            width: 40%;
            img{
              height: 90px;
            }
          }
          &:last-child{
            width: 60%;
            img{
              height: 100px;
            }
          }
        }
      }
    }
    @media(max-width: 768px){
      .flex-row{
        >div{
          &:first-child{
            width: 40%;
            img{
              height: 90px;
            }
          }
          &:last-child{
            width: 60%;
            img{
              height: 100px;
            }
          }
        }
      }
    }
    @media(max-width: 567px){
      .flex-row{
        align-items: top;
        width: 100%;
        >div{
          padding: 0 15px;
          &:first-child{
            width: 30%;
            img{
              height: 85px;
            }
          }
          &:last-child{
            width: 70%;
            img{
              height: 70px;
            }
          }
        }
      }
    }
  }
  .w-50 {
    width: 50%;
  }
  .w-33{
    width: 33.33%;
  }
}
</style>
