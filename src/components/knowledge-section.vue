<script setup>
  import {onMounted, ref, watchEffect} from "vue"
  import gsap from "gsap"
  import ScrollTrigger from "gsap/ScrollTrigger"

  // Calc height of box
  const devops = ref(null)
  const developer = ref(null)

  watchEffect(() => {
    if (developer.value && devops.value) gsap.set("#flipper", {height: Math.max(developer.value.offsetHeight, devops.value.offsetHeight) + 10})
  })

  // Flip animation
  gsap.registerPlugin(ScrollTrigger)
  let page
  onMounted(() => {
    gsap
      .timeline({
        scrollTrigger: {
          trigger: "#knowledge",
          start: "top center",
          scrub: false,
          once: true
        }
      })
      .to("#knowledge", {duration: 0.5, scale: 0.8, ease: "Power2.easeInOut"}, "start")
      .to("#flipper", {duration: 0.4, rotationY: (page = !page ? -180 : 0), ease: "Power2.easeInOut"}, "start+=0.7")
      .to("#knowledge", {duration: 0.5, scale: 1, ease: "Power2.easeInOut"}, "start+=1.2")
  })

  function nextKnowledgeField() {
    gsap
      .timeline()
      .to("#knowledge", {duration: 0.5, scale: 0.8, ease: "Power2.easeInOut"}, "start")
      .to("#flipper", {duration: 0.4, rotationY: (page = !page ? -180 : 0), ease: "Power2.easeInOut"}, "start+=0.7")
      .to("#knowledge", {duration: 0.5, scale: 1, ease: "Power2.easeInOut"}, "start+=1.2")
  }
</script>

<template>
  <div id="knowledge-section" class="is-flex">
    <img alt="Laptop" id="laptop" class="print-hidden" src="@/assets/laptop.png" />
    <div id="knowledge">
      <div id="flipper" class="box">
        <section ref="developer" id="developer">
          <div class="is-flex">
            <h3>Knowledge</h3>
            <img alt="Flip button" class="print-hidden flip-button" src="@/assets/flip.png" width="70" height="70" @click="nextKnowledgeField" />
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
        <section ref="devops" id="devops">
          <div class="is-flex print-hidden">
            <h3>Knowledge</h3>
            <img alt="Flip button" class="flip-button" src="@/assets/flip.png" width="70" height="70" @click="nextKnowledgeField" />
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
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @import "src/styles/shared";

  #knowledge-section {
    #knowledge {
      margin-top: 200px;
      margin-right: 10vw;
      perspective: 1000px;

      #flipper {
        border-color: #dc143c;
        transition: 0.6s;
        transform-style: preserve-3d;

        ::v-deep(div) {
          justify-content: space-between;
        }

        #developer,
        #devops {
          backface-visibility: hidden;
          position: absolute;
          top: 0;
          left: 0;
          width: 40vw;
          padding: 20px;

          .flip-button {
            width: 50px;
            height: 50px;
            margin-top: 20px;
            align-self: flex-end;
            cursor: pointer;
          }
        }

        #developer {
          z-index: 2;
          transform: rotateY(180deg);
        }

        #devops {
          transform: rotateY(0deg);
        }
      }
    }

    #laptop {
      margin-top: 500px;
      margin-left: 10vw;
      margin-right: 100px;
      width: auto;
      height: 400px;
      pointer-events: none;
    }
  }

  @media print {
    #knowledge-section {
      display: block !important;

      #knowledge {
        margin: 0 !important;

        #flipper {
          transform: none !important;

          #developer,
          #devops {
            width: auto !important;
            position: static !important;
            transform: none !important;
          }
        }
      }
    }
  }

  @media screen and (max-width: 1280px) {
    #knowledge-section {
      #knowledge {
        width: 100% !important;
        margin: 80px 100px 0 !important;

        #flipper {
          width: auto !important;
          margin: 0 !important;
          section {
            width: calc(100% - 40px) !important;
            margin: 0 auto !important;
          }
        }
      }

      #laptop {
        display: none;
      }
    }
  }

  @media screen and (max-width: 600px) {
    #knowledge-section {
      #knowledge {
        margin: 30px 10px 0 !important;
      }
    }
  }
</style>
