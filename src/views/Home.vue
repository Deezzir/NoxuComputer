<template>
    <div>
        <section class="hero is-primary is-bold is-fullheight-with-navbar">
            <div class="hero-body">
                <div class="container">
                    <h1 class="title is-size-1">
                        ShpagGA
                    </h1>
                    <h2 class="subtitle is-size-6-mobile">
                        ShpagGA - become an admin at affordable price!<br>
                        Support of Minecraft, Terraria, Rust, CS:GO, TF2...<br>
                        Full access to the server via powerful control panel<br>
                        Free support, consulting and help in setup.<br>
                        All versions of:.<br>
                        Forge, Paper, Sponge, Bungeecord;<br>
                        TShock, tModLoader and other
                    </h2>
                    <a href="#plansSection" class="button is-primary is-inverted is-outlined is-large">
                        <b-icon icon="cart"/>
                        <span>Pricing</span>
                    </a>
                    <hr>
                    <p>Don't be shy, just ask:</p>
                    <div class="buttons">
                        <a class="button is-secondary is-large"
                           href="https://www.instagram.com/shpag.ga">
                            <b-icon icon="instagram"/>
                            <span>shpag.ga</span>
                        </a>
                    </div>
                </div>
            </div>
        </section>
        <section class="hero is-primary parallax">
            <div class="hero-body">
                <div class="has-text-justified-desktop">
                    <h1 class="title is-size-2 is-size-3-mobile">Capabilities
                        <b-icon icon="developer-board" size="is-medium"/>
                    </h1>
                    <p class="is-size-5 is-size-6-mobile">
                        Our powerful servers are located in Germany and Finland and are ready to host your own private
                        or public game server
                    </p>
                    <hr>
                    <div class="column box is-4">
                        <p class="is-size-5 is-size-6-mobile">
                            <b-icon icon="memory"/>
                            Intel Xeon E5-2630v4
                        </p>
                        <p class="is-size-5 is-size-6-mobile">
                            <b-icon icon="chip"/>
                            60 Gb
                        </p>
                        <p class="is-size-5 is-size-6-mobile">
                            <b-icon icon="harddisk"/>
                            1.5 TB 100% SSD
                        </p>
                        <p class="is-size-5 is-size-6-mobile">
                            <b-icon icon="flag"/>
                            Germany
                        </p>
                        <p class="is-size-5 is-size-6-mobile">
                            <b-icon icon="ethernet"/>
                            1 GBpS
                        </p>
                    </div>
                </div>
            </div>
        </section>
        <section class="section" id="plansSection">
            <div class="container">
                <h1 class="title is-size-2 is-size-3-mobile">Pricing
                    <b-icon icon="cash" size="is-medium"/>
                </h1>
                <div class="pricing-table is-comparative">
                    <div class="pricing-plan is-features">
                        <div class="plan-header">Resources</div>
                        <div class="plan-price"><span class="plan-price-amount">&nbsp;</span></div>
                        <div class="plan-items">
                            <div class="plan-item">CPU Cores</div>
                            <div class="plan-item">Available RAM</div>
                            <div class="plan-item">SSD</div>
                            <div class="plan-item">Control panel</div>
                            <div class="plan-item">File access</div>
                            <div class="plan-item">Console</div>
                            <div class="plan-item">Sub-users</div>
                            <div class="plan-item">Ports</div>
                            <div class="plan-item">SWAP memory</div>
                            <div class="plan-item">MySQL/PostGreSQL</div>
                            <div class="plan-item">Dedicated IP</div>
                        </div>
                        <div class="plan-footer">

                        </div>
                    </div>

                    <div :class="'pricing-plan ' + plan.klass" v-for="plan in plans">
                        <div class="plan-header">{{plan.name}}</div>
                        <div class="plan-price"><span class="plan-price-amount"><span
                                class="plan-price-currency">{{plan.currency}}</span>{{plan.price}}</span>/month
                        </div>
                        <div class="plan-items">
                            <div class="plan-item" data-feature="CPU">{{plan.cpu}}</div>
                            <div class="plan-item" data-feature="RAM">{{plan.mem}}</div>
                            <div class="plan-item" data-feature="SSD">{{plan.ssd}} Gb</div>
                            <div class="plan-item" data-feature="Control panel">Included</div>
                            <div class="plan-item" data-feature="File acceess">Included</div>
                            <div class="plan-item" data-feature="Console">Included</div>
                            <div class="plan-item" data-feature="Sub-user">Included</div>
                            <div class="plan-item" data-feature="Ports">{{plan.ports}}</div>
                            <div class="plan-item" data-feature="SWAP memory">{{plan.swap}} Gb</div>
                            <div class="plan-item" data-feature="MySQL/PGSQL">{{value(plan.db, ' DB')}}</div>
                            <div class="plan-item" data-feature="IP">{{value(plan.ip, '')}}</div>
                        </div>
                        <div class="plan-footer">
                            <!--<button class="button is-fullwidth">В</button>-->
                            <a href="https://t.me/grigg191" class="button">
                                <b-icon icon="instagram"/>
                                <span>Quote</span></a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="hero" ref="games" id="gamesSection">
            <div class="hero-body">
                <div class="container has-text-justified">
                    <h1 class="title is-size-2 is-size-3-mobile">
                        Available games
                        <b-icon icon="gamepad-variant" size="is-medium"/>
                    </h1>
                    <div class="columns is-multiline">
                        <div class="column is-4" v-for="game in games">
                            <div class="box" id="scrollTo">
                                <h1 class="title is-size-4">
                                    {{game.name}}&nbsp;
                                    <b-icon :icon="game.icon" size="is-small"/>
                                </h1>
                                <hr>
                                <div class="tags">
                                    <span class="tag is-primary" v-for="variation in game.list">
                                        {{variation}}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <p class="is-size-5 is-size-6-mobile">
                        If you haven't found your favorite game in this list, just message us and we will try to fix it!
                    </p>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
  // @ is an alias to /src
  import Navbar from "@/components/Navbar"

  export default {
    name: 'home',
    components: {Navbar},
    data() {
      return {
        games: [
          {
            name: 'Minecraft',
            icon: 'minecraft',
            list: [
              'Forge',
              'BungeeCord',
              'SpongeVanilla',
              'Paper Vanilla',
              'Vanilla',
              'Tekkit',
              'FTB',
              'Bedrock',
              'Nukkit',
              'PocketMine'
            ]
          },
          {
            name: 'Source Engine',
            icon: 'steam',
            list: [
              'Counter-Strike: Global Offensive',
              'Garry\'s mod',
              'Insurgency',
              'Team Fortress 2',
              'Ark: Survival Evolved',
              'Starbound',
              'Pixark',
              '7 Days to Die'
            ]
          },
          {
            name: 'Terraria',
            icon: 'pine-tree',
            list: [
              'tShock',
              'tModLoader'
            ]
          },
          {
            name: 'Rust',
            icon: 'cogs',
            list: [
              'Rust server'
            ]
          },
          {
            name: 'Factorio',
            icon: 'factory',
            list: [
              'Factorio server'
            ]
          },
          {
            name: 'Grand Theft Auto',
            icon: 'car',
            list: [
              'FiveM',
              'Rage MP',
              'GTA SA:MP',
              'MTA SA'
            ]
          }
        ],
        plans: [
          {
            name: 'Nano',
            klass: '',
            currency: '$',
            price: 4,
            mem: "1024 Mb",
            cpu: "1 core",
            ssd: 25,
            ports: 2,
            swap: 2,
            db: ''
          },
          {
            name: 'Micro',
            klass: 'is-active',
            currency: '$',
            price: 7,
            mem: "2512 Mb",
            cpu: "2 cores",
            ssd: 40,
            ports: 3,
            swap: 5,
            db: '1'
          },
          {
            name: 'Standart',
            klass: 'is-warning',
            currency: '$',
            price: 15,
            mem: "5 Gb",
            cpu: "3 cores",
            ssd: 80,
            ports: 5,
            swap: 8,
            db: 2
          },
          {
            name: 'Overclocked',
            klass: 'is-danger',
            currency: '$',
            price: 25,
            mem: "16 Gb",
            cpu: "6 cores",
            ssd: 320,
            ports: "unlimited",
            swap: "unlimited",
            ip: 1,
            db: "unlimited"
          },
        ]
      }
    },
    methods: {
      value(value, suffix) {
        return value ? value + suffix : '-'
      }
    }
  }
</script>

<style lang="scss" scoped>
    .parallax {
        /* The image used */
        background-image: url("../assets/minecraft.jpg");

        /* Set a specific height */
        // height: 500px;

        /* Create the parallax scrolling effect */
        background-attachment: fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    @media screen and (max-width: 479px) {
        .parallax {
            -moz-background-size: auto;
            -webkit-background-size: auto;
            background-attachment: fixed;
            background-position: top;
            background-size: auto;
        }
    }

    .parallax::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: black;
        opacity: 50%;
        z-index: -1;
    }

</style>
