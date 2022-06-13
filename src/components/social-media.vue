<template>
  <div id="social-media">
    <div id="social">
      <a target="_blank" href="https://github.com/NowakMateusz/bio/"><img alt="GitHub link" src="@/assets/github.png" /></a>
      <a target="_blank" href="https://www.linkedin.com/in/mateusz-nowak-4578aaaa"><img alt="LinkedIn link" src="@/assets/linkedin.png" /></a>
      <a onclick="window.print()"><img alt="Print CV" src="@/assets/printer.png" /></a>
    </div>
  </div>
</template>
<style lang="scss" scoped>
  #social-media {
    position: sticky;
    top: 20px;
    left: 20px;

    #social {
      display: flex;
      flex-direction: column;
      a {
        width: auto;
        cursor: pointer;

        img {
          padding: 10px 15px;
          height: 4rem;
        }
      }
    }
  }

  @media screen and (max-width: 1280px) {
    #social-media {
      top: 7px;
      left: 7px;
    }
  }

  @media screen and (max-width: 600px) {
    #social-media {
      position: static;
    }
  }
</style>
