<script setup>
  import {onMounted, watchEffect} from "vue"
  import gsap from "gsap"

  const props = defineProps(["traX", "traY"])

  onMounted(() => {
    // Name fill animation
    watchEffect(() => {
      gsap.set("#name", {backgroundPositionX: props.traX + "%", backgroundPositionY: props.traY + "%"})
    })

    // Coffee animation
    const steams = ["#steam-left", "#steam-right", "#steam-mid"]
    gsap.to(steams, {duration: 2, scaleX: 0, yoyo: true, repeat: -1, force3D: true, ease: "Linear.easeOut"})
    gsap.timeline({repeat: -1, yoyo: true}).set(steams, {opacity: "0", ease: "Linear.easeInOut"}).to(steams, {duration: 1.5, opacity: ".75", ease: "Linear.easeInOut"})
    gsap.timeline({repeat: -1}).to(steams, {duration: 2, stagger: 0.5, y: "-=50px", ease: "Linear.easeOut"})
  })
</script>

<template>
  <div id="heading-section" class="is-flex">
    <div class="coffee print-hidden">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" xml:space="preserve">
        <g id="steams">
          <path
            id="steam-left"
            fill="#ECEFF0"
            d="M377.611,203.07c-25.395,8.346-80.709,47.844-41.081,74.058
		c44.527,28.808,38.123,33.269-6.917,72.483c23.679-9.33,82.718-49.811,38.063-73.173
		C320.997,252.822,338.488,233.276,377.611,203.07C373.292,204.49,370.435,208.611,377.611,203.07z"
          />
          <path
            id="steam-right"
            fill="#ECEFF0"
            d="M617.61,203.07c-25.398,8.347-80.704,47.841-41.081,74.058
		c44.526,28.807,38.123,33.269-6.916,72.483c23.678-9.33,82.718-49.811,38.063-73.173
		C560.995,252.824,578.487,233.273,617.61,203.07C613.291,204.49,610.434,208.611,617.61,203.07z"
          />
          <path
            id="steam-mid"
            fill="#ECEFF0"
            d="M503.39,151c-29.594,10.944-101.875,60.753-51.809,93.649
		c11.829,7.624,49.646,13.698,44.947,34.054c-5.715,25.162-36.23,45.828-54.915,60.909c28.3-12.377,103.601-63.641,48.103-92.404
		C428.52,216.343,450.766,188.6,503.39,151C497.933,153.018,493.944,157.749,503.39,151z"
          />
        </g>
      </svg>
      <img alt="Coffee" src="@/assets/coffee.png" />
    </div>
    <div class="heading">
      <h1 id="name">Mateusz Nowak</h1>
      <div id="flip" class="print-hidden">
        <div><div>DevOps</div></div>
        <div><div>Full-stack developer</div></div>
      </div>
      <div id="print-github-url">https://nowakmateusz.github.io/</div>
    </div>
    <div id="print-github-qrcode">
      <img alt="Github QR code" src="@/assets/qrcode.png" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @import "src/styles/shared";
  @import url("https://fonts.googleapis.com/css?family=Raleway:400,800,900");

  #heading-section {
    margin-top: 100px;
    justify-content: center;

    svg {
      width: 300px;
      display: block;
      margin: -100px -50px -200px;
    }

    img {
      height: 200px;
    }

    .heading {
      font-family: "Raleway", monospace;
      font-weight: bold;
      text-transform: uppercase;
      text-align: center;
      display: block;

      h1 {
        color: transparent;
        font-size: 3em;
        background: url("https://phandroid.s3.amazonaws.com/wp-content/uploads/2014/05/rainbow-nebula.jpg") repeat 40% 50%;
        -webkit-background-clip: text;
        margin-bottom: 0;
      }

      #print-github-url {
        display: none;
      }

      #flip {
        font-size: 1.5em;
        height: 50px;
        overflow: hidden;
      }

      #flip > div > div {
        color: #fff;
        padding: 10px 12px;
        height: 45px;
        margin-bottom: 45px;
        display: inline-block;
      }

      #flip div:first-child {
        animation: show 5s linear infinite;
      }

      #flip div:first-child div {
        background: #4ec7f3;
      }

      #flip div:last-child div {
        background: #dc143c;
      }

      @keyframes show {
        0% {
          margin-top: -180px;
        }
        5% {
          margin-top: -90px;
        }
        33% {
          margin-top: -90px;
        }
        38% {
          margin-top: -90px;
        }
        66% {
          margin-top: -90px;
        }
        71% {
          margin-top: 0;
        }
        99.99% {
          margin-top: 0;
        }
        100% {
          margin-top: -180px;
        }
      }
    }

    #print-github-qrcode {
      display: none;
    }
  }

  @media print {
    #heading-section {
      margin: 0 !important;
      left: 0 !important;
      justify-content: space-between !important;
    }

    .heading {
      h1 {
        color: black !important;
      }

      #print-github-url {
        display: block !important;
        text-transform: lowercase !important;
        text-align: right;
        font-family: "Source Sans Pro", -apple-system, system-ui, sans-serif;
        margin-bottom: 5px;
      }
    }
    #print-github-qrcode {
      display: inline-block !important;
    }
  }

  @media screen and (max-width: 1280px) {
    #heading-section {
      margin: 0 !important;
    }
  }

  @media screen and (max-width: 780px) {
    #heading-section {
      margin-top: -170px !important;
      flex-direction: column;
      align-items: center;
    }
  }
</style>
