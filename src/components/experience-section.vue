<script setup></script>

<template>
  <div id="experience-section" class="is-flex">
    <div id="experience" class="box">
      <h3>Experience</h3>
      <section>
        <ul>
          <li>
            <b>Poznan University of Technology (employee of central IT department)</b><span>09/2013 – Present</span>
            <blockquote>
              I was hired as System Administrator, in meantime I was promoted to IT Specialist/DevOps and next to Section Manager (in end of 2022 head of 18 persons) – my Section handle
              hundreds of hardware and virtual machines/servers. Job on university learn me how to handle big and complex IT ecosystems.
            </blockquote>
          </li>
          <li>
            <b>Partner IT Mateusz Nowak (owner)</b><span>04/2010 – Present</span>
            <blockquote>
              The company is target on outsourcing IT. Customers don’t change and are on long-term agreements. Customers are: high school, notary office, some production companies. On
              those customers I recreated from scratch and maintained whole IT structures, in some cases I develop software. In meantime my company changed to Partner IT – Magdalena
              Nowak i Mateusz Nowak s.c. Company don’t have other permanent employees and when is the need I'm employing under civil contracts to special tasks.
            </blockquote>
          </li>
          <li>
            <b>DomData AG Sp. z o.o. (employee of software development section)</b><span>07/2013 – 08/2013</span>
            <blockquote>Programmer .NET C# - where I was focused on creating bank targeted software.</blockquote>
          </li>
          <li>
            <b>Coleos S.A. (employee on civil contract)</b><span>09/2012 – 09/2013</span>
            <blockquote>System administrator, program architect, programmer ASP.NET C# - I was focused on creating advertisement software.</blockquote>
          </li>
          <li>
            <b>PC Service D. Nogaj and S. Łabowski s.c. (employee of outsourcing IT section)</b><span>04/2009 – 09/2009</span>
            <blockquote>My job was IT care, servicing and system administration delivered to company customers.</blockquote>
          </li>
        </ul>
      </section>
    </div>
    <img alt="Fancy IT specialist" class="print-hidden" src="@/assets/business.png" />
  </div>
</template>

<style lang="scss" scoped>
  @import "src/styles/shared";

  #experience-section {
    #experience {
      margin-top: 200px;
      left: 10vw;
      border-color: #4ec7f3;

      span {
        float: right;
        margin-right: 20px;
      }
    }

    img {
      margin-top: 300px;
      margin-right: 10vw;
      margin-left: 100px;
      width: auto;
      height: 400px;
      pointer-events: none;
    }
  }

  @media print {
    #experience {
      margin: 0 !important;
      left: 0 !important;
    }
  }

  @media screen and (max-width: 1280px) {
    #experience-section {
      #experience {
        width: auto;
        position: static;
        margin: 80px 100px 0 !important;
      }

      img {
        display: none;
      }
    }
  }

  @media screen and (max-width: 600px) {
    #experience-section {
      #experience {
        margin: 30px 10px 0 !important;
      }
    }
  }
</style>
