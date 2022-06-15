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
              I was hired as a System Administrator, promoted to IT Specialist/DevOps and now being in a role of Section Manager (in end of 2022 head of 18 employees) – my Section manages hundreds of physical and Virtual Machines/Servers. The job on the University taught me how to handle large and complex IT ecosystems.
            </blockquote>
          </li>
          <li>
            <b>Partner IT Mateusz Nowak (owner)</b><span>04/2010 – Present</span>
            <blockquote>
              The Company is targeted on IT outsourcing. The Customers are on long-term agreements and don’t change. Amongst them are: a high school, a notary office, and a few production companies. For these Customers I have developed from scratch and maintained entire IT structures, and occasionally developed software. At some point, my Company transformed to “Partner IT – Magdalena Nowak i Mateusz Nowak s.c.” There are no other permanent employees - civil contracts for special tasks are concluded as required.
            </blockquote>
          </li>
          <li>
            <b>DomData AG Sp. z o.o. (employee of software development section)</b><span>07/2013 – 08/2013</span>
            <blockquote>Programmer .NET C# - I was focusing on bank targeted software development.</blockquote>
          </li>
          <li>
            <b>Coleos S.A. (employee on civil contract)</b><span>09/2012 – 09/2013</span>
            <blockquote>System administrator, program architect, programmer ASP.NET C# - I was working on advertisement software development.</blockquote>
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
