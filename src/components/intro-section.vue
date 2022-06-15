<template>
  <div id="intro-section" class="is-flex">
    <div id="intro" class="box">
      <h3>Feel it!</h3>
      <p>Computers are my life passion. I got my first one in high school and, in just few months, I have dived deep into it. I started with Windows, where I was developing first tool apps.</p>
      <p>
        The avalanche flew quicker and quicker. I began exploring new areas: other OS, new languages, different technologies. Still in high school, I started making extra money by repairing computers, resolving system issues, diagnosing, and replacing broken hardware.
      </p>
      <p>This is my history, and I wouldn’t be surprised if we share it!</p>
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
