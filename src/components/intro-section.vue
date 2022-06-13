<template>
  <div id="intro-section" class="is-flex">
    <div id="intro" class="box">
      <h3>Feel it!</h3>
      <p>Computers are my life passion. In high school I got my first one. In a few months I dive deep in to them. I start knowing Windows, start creating first tool apps.</p>
      <p>
        An avalanche flew quicker and quicker. I learn new things: new OS, new languages, new technologies. In the same school I start making extra money by repairing computers, some
        system issues, diagnose and change broken hardware.
      </p>
      <p>This was my history, and this is probably yours too!</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @import "src/styles/shared";

  #intro-section {
    justify-content: end;
    margin-right: 100px;

    #intro {
      margin-top: 200px;
      border-color: #42c58a;
    }
  }

  @media screen and (max-width: 1280px) {
    #intro-section {
      #intro {
        margin-top: 100px !important;
      }
    }
  }

  @media screen and (max-width: 900px) {
    #intro-section {
      width: auto !important;
      margin: 80px 100px 0 !important;
      #intro {
        width: auto !important;
      }
    }
  }

  @media screen and (max-width: 600px) {
    #intro-section {
      width: auto !important;
      margin: 30px 10px 0 !important;
      #intro {
        width: auto !important;
      }
    }
  }
</style>
