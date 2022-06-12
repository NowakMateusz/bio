<script setup>
  import {onMounted, ref, watchEffect} from "vue"
  import gsap from "gsap"

  const devops = ref(null)
  const developer = ref(null)

  watchEffect(() => {
    if (developer.value && devops.value) gsap.set(".flipper", {height: Math.max(developer.value.offsetHeight, devops.value.offsetHeight)})
  })

  let page
  function nextKnowledgeField() {
    page = !page
    const rotation = page ? -180 : 0
    gsap
      .timeline()
      .to("#knowledge", {duration: 0.5, scale: 0.8, ease: "Power2.easeInOut"}, "start")
      .to(".flipper", {duration: 0.4, rotationY: rotation, ease: "Power2.easeInOut"}, "start+=0.7")
      .to("#knowledge", {duration: 0.5, scale: 1, ease: "Power2.easeInOut"}, "start+=1.2")
  }

  onMounted(() => {
    const steams = ["#steam-left", "#steam-right", "#steam-mid"]

    gsap.to(steams, {duration: 2, scaleX: 0, yoyo: true, repeat: -1, force3D: true, ease: "Linear.easeOut"})
    gsap.timeline({repeat: -1, yoyo: true}).set(steams, {opacity: "0", ease: "Linear.easeInOut"}).to(steams, {duration: 1.5, opacity: ".75", ease: "Linear.easeInOut"})
    gsap.timeline({repeat: -1}).to(steams, {duration: 2, stagger: 0.5, y: "-=50px", ease: "Linear.easeOut"})
  })

  function mousemove(event) {
    const traX = (4 * event.pageX) / 570 + 40
    const traY = (4 * event.pageY) / 570 + 50
    gsap.set("#name", {backgroundPositionX: traX + "%", backgroundPositionY: traY + "%"})
  }
</script>
<template>
  <div id="main" @mousemove="mousemove">
    <div class="social-media">
      <a href="https://github.com/NowakMateusz"><img alt="GitHub" class="icons github" src="@/assets/github.png" /></a>
      <a href="https://www.linkedin.com/in/mateusz-nowak-4578aaaa"><img alt="LinkedIn" class="icons linkedin" src="@/assets/linkedin.png" /></a>
    </div>
    <div id="heading-section" class="is-flex">
      <div class="coffee">
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
        <div id="flip">
          <div><div>DevOps</div></div>
          <div><div>Full-stack developer</div></div>
        </div>
      </div>
    </div>
    <div id="intro" class="box">
      <h3>Feel it!</h3>
      <p>Computers are my life passion. In high school I got my first one. In a few months I dive deep in to them. I start knowing Windows, start creating first tool apps.</p>
      <p>
        An avalanche flew quicker and quicker. I learn new things: new OS, new languages, new technologies. In the same school I start making extra money by repairing computers, some
        system issues, diagnose and change broken hardware.
      </p>
      <p>This was my history, and this is probably yours too!</p>
    </div>
    <div id="experience-section" class="is-flex">
      <div id="experience" class="box">
        <h3>Experience</h3>
        <section>
          <ul>
            <li>
              <b>Poznan University of Technology (employee of central IT department)</b><span>09/2013 – Present</span>
              <blockquote>
                I was hired as System Administrator, in meantime I was promoted to IT Specialist/DevOps and next to Section Manager (in end of 2022 head of 18 persons) – my Section
                handle hundreds of hardware and virtual machines/servers. Job on university learn me how to handle big and complex IT ecosystems.
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
      <img src="@/assets/business.png" />
    </div>
    <div id="knowledge-section" class="is-flex">
      <div id="flip-images">
        <img id="laptop" src="@/assets/laptop.png" />
        <img id="server" src="@/assets/server.png" />
      </div>
      <div id="knowledge" class="flip-container">
        <div class="flipper box">
          <section ref="devops" id="devops">
            <div class="is-flex">
              <h3 ref="knowledgeTitle">Knowledge</h3>
              <img src="@/assets/flip.png" width="70" height="70" @click="nextKnowledgeField" />
            </div>
            <h4>DevOps/System Administrator field</h4>
            <ul>
              <li>
                <p>Advanced handling of platforms:</p>
                <p>Microsoft Windows, Windows Servers UNIX*: RHEL / Debian / Ubuntu / openSUSE / XenServer, FreeBSD, NetBSD, pfSense.</p>
              </li>
              <li>
                <p>Handling and managing networks IPv4/IPv6:</p>
                <p>LAN, VLAN, WLAN, VPN</p>
              </li>
              <li>
                <p>Knowledge of script languages:</p>
                <p>Bash/Zsh, Python, JavaScript (NodeJS)</p>
              </li>
              <li>
                <p>Configuring and managing services and technologies such as:</p>
                <p>DHCP, DNS, SSH, SNMP, POP, IMAP, SMTP, HTTP, FTP, NTP, VNC, RDP, OpenLDAP, SMB, ActiveDirectory, LVM, ZFS, iSCSI, DRBD</p>
              </li>
              <li>
                <p>Configuring WebServers:</p>
                <p>Apache, nginx, Tomcat, WildFire, Microsoft IIS</p>
              </li>
              <li>
                <p>Virtualization ecosystems:</p>
                <p>VMware, Xen, Hyper-V, KVM/QEMU/oVirt</p>
              </li>
              <li>
                <p>Management of Windows Failover Clusters:</p>
                <p>Windows Server Failover Clustering, Pacemaker, Keepalived</p>
              </li>
              <li>
                <p>Creating Docker images and Helm charts</p>
              </li>
              <li>
                <p>Management of private Kubernetes clusters with:</p>
                <p>Istio Mesh, cert-manager, ProxySQL, Docker registry (Harbor), Rancher, Jenkins, GitLab Runner CI/CD</p>
              </li>
              <li>
                <p>Management of projects:</p>
                <p>private GitLab servers, Redmine, Kayako</p>
              </li>
              <li>
                <p>Management of Zabbix monitoring system</p>
              </li>
              <li>
                <p>Management of CheckPoint, Netasq, pfSense, Windows, native iptables/nftables firewalls</p>
              </li>
              <li>
                <p>Knowledge of issues related to security systems and services</p>
              </li>
            </ul>
          </section>
          <section ref="developer" id="developer">
            <div class="is-flex">
              <h3>Knowledge</h3>
              <img src="@/assets/flip.png" width="70" height="70" @click="nextKnowledgeField" />
            </div>
            <h4>Developer field</h4>
            <div>
              <h5>Javascript (Node.js)</h5>
              <span>Libraries</span>
              <ul>
                <li>jQuery</li>
                <li>DataTables</li>
                <li>Lodash</li>
                <li>GSAP</li>
                <li>Vuex</li>
                <li>VueRouter</li>
                <li>Axios</li>
                <li>Apollo</li>
              </ul>
              <ul>
                <li>Express.js</li>
                <li>Sequelize</li>
              </ul>
              <span>Frameworks</span>
              <ul>
                <li>Vue (Option and Composition API)</li>
                <li>Bootstrap</li>
                <li>Buefy</li>
                <li>Oruga</li>
              </ul>
              <span>npm/yarn/pnpm, vite, prettier... and many more less complex</span>
              <h5>ASP .NET C#</h5>
              <ul>
                <li>MVC/Razor</li>
                <li>Entity Framework</li>
              </ul>
              <h5>CSS/SCSS</h5>
              <ul>
                <li>Bootstrap</li>
                <li>Bulma</li>
              </ul>
            </div>
            <div>
              <h5>Knowledge of technology</h5>
              <ul>
                <li>REST, GraphQL, SOAP, Websockets</li>
                <li>OAuth2 (Implicit, Code Flow and Refresh tokens), JWT, Basic Auth</li>
                <li>Cryptography: AES/RSA, MAC/HMAC, Hash algorithms</li>
              </ul>
            </div>
            <div>
              <h5>Databases/Storage</h5>
              <ul>
                <li>MySQL/MariaDB</li>
                <li>PostgreSQL</li>
                <li>MS SQL</li>
                <li>Oracle</li>
                <li>S3 Storage</li>
              </ul>
            </div>
            <div>
              <p>I have less experience as well on other languages: PHP, Ruby</p>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;700&display=swap");

  body {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-family: "Source Sans Pro", -apple-system, system-ui, sans-serif;
  }
</style>
<style scoped lang="scss">
  @import url("https://fonts.googleapis.com/css?family=Raleway:400,800,900");

  #main {
    margin-bottom: 50px;
  }

  .is-flex {
    display: flex;
    justify-content: space-between;
  }

  .box {
    position: relative;
    width: 40vw;
    padding: 20px;
    border-radius: 0 0 5px 5px;
    box-shadow: rgba(50, 50, 93, 0.25) 0 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
    border-top: solid 4px;
  }

  .social-media {
    position: sticky;
    display: flex;
    flex-direction: column;
    top: 20px;
    left: 20px;

    .icons {
      padding: 10px 15px;
      height: 4rem;
    }
  }

  #heading-section {
    margin-top: 200px;
    margin-left: 30vw;
    justify-content: normal;

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
  }

  #intro {
    margin-top: 200px;
    left: 50vw;
    border-color: #42c58a;
  }

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
    }
  }

  #knowledge-section {
    #knowledge {
      margin-top: 200px;
      margin-right: 10vw;
      perspective: 1000px;

      .flipper {
        border-color: #dc143c;
        transition: 0.6s;
        transform-style: preserve-3d;
        position: relative;

        h3 {
          font-size: 1.2em;
        }

        img {
          margin-top: 20px;
          align-self: flex-end;
          cursor: pointer;
        }

        #developer,
        #devops {
          backface-visibility: hidden;
          position: absolute;
          top: 0;
          left: 0;
          width: 40vw;
          padding: 20px;
        }

        #developer {
          z-index: 2;
          transform: rotateY(0deg);
        }

        #devops {
          transform: rotateY(180deg);
        }
      }
    }

    #flip-images {
      img {
        margin-top: 500px;
        margin-left: 10vw;
        margin-right: 100px;
        width: auto;
        height: 400px;
      }

      #server {
        display: none;
      }
    }
  }
</style>
