<template>
    <header class="header">
        <div class="header-top">
            <div class="header-top-wrapper">
                <span>Empowering entreprenerus to launch their own trading systems.</span>
                <a href="javascript:void(0);" class="link link_phone">
                    <svg width="22" height="22" viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M11.0375 0C4.95563 0 0 4.95563 0 11.0375C0 17.1195 4.95563 22 11.0375 22C17.1195 22 22 17.1195 22 11.0375C22 4.95563 17.1195 0 11.0375 0ZM12.2389 14.1911L12.6143 14.4915C12.6143 14.4915 12.7645 14.7167 13.215 14.5666C13.6655 14.3413 14.7918 13.0648 14.7918 13.0648C14.7918 13.0648 15.3174 12.6143 15.843 13.0648C16.4437 13.5154 18.2457 15.3174 18.2457 15.3174C18.2457 15.3174 18.5461 15.843 18.1706 16.3686C17.7201 16.8191 15.843 18.2457 15.843 18.2457C15.843 18.2457 15.0171 18.6212 14.041 17.8703C12.314 16.4437 5.55631 9.68601 4.12969 7.95904C3.37884 6.98294 3.82935 6.157 3.82935 6.157C3.82935 6.157 5.18089 4.27986 5.70648 3.90444C6.23208 3.45393 6.68259 3.82935 6.68259 3.82935C6.68259 3.82935 8.48464 5.6314 8.93515 6.157C9.38567 6.75768 8.93515 7.20819 8.93515 7.20819C8.93515 7.20819 7.6587 8.33447 7.50853 8.78498C7.28328 9.2355 7.50853 9.46075 7.50853 9.46075L7.88396 9.83618C9.31058 11.2628 10.7372 12.6894 12.2389 14.1911Z"
                            fill="#547966" />
                    </svg>
                    <span>8 888 888 88 88</span>
                </a>
            </div>

        </div>
        <div class="header-bottom">
            <div class="header-bottom-wrapper">
                <a href="javascript:void(0);" class="logo">
                    <svg width="39" height="38" viewBox="0 0 39 38" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M38.4214 37.8754H28.8393C28.7463 37.8754 28.6843 37.8443 28.6223 37.8131C28.5603 37.7508 28.4982 37.6885 28.4672 37.6262L20.7457 19.6229L20.2496 18.5016V18.2213L10.9776 37.2836C10.9465 37.3459 10.8845 37.4082 10.8225 37.4394C10.7605 37.4705 10.6675 37.5016 10.6054 37.5016H0.403132C0.341111 37.5016 0.248079 37.4705 0.217069 37.4394C0.155049 37.4082 0.0930292 37.3459 0.0620192 37.3148C0.0310091 37.2525 0 37.1902 0 37.1279C0 37.0656 -4.73638e-07 36.9721 0.0310096 36.9098L17.5827 0.934426C17.7377 0.654098 17.9238 0.404933 18.2029 0.249196C18.482 0.0934578 18.7921 0 19.1022 0H26.4826C26.7617 0 27.0408 0.0623179 27.2888 0.218056C27.5369 0.342646 27.754 0.560656 27.909 0.778688C28.0641 1.02787 28.1571 1.30819 28.1571 1.58852C28.1571 1.86884 28.1261 2.1492 27.9711 2.42952L24.746 8.53443V8.34756V8.53443L25.3662 9.84262L38.7626 37.1902C38.8556 37.2525 38.9486 37.3459 38.9796 37.4394C39.0106 37.564 39.0106 37.6885 38.9486 37.782C38.8866 37.8754 38.7936 37.9688 38.7005 38C38.6385 37.9377 38.5145 37.9377 38.4214 37.8754Z"
                            fill="white" />
                    </svg>
                </a>
                <ul class="header-links">
                    <li class="header-links__item" v-for="link in links" :key="link">
                        <a href="javascript:void(0);" class="header-lnks__link">{{ link }}</a>
                    </li>
                </ul>
                <div class="mobile-menu-wrapper">
                    <a href="javascript:void(0);" class="burger-btn" @click="toggleMenu">
                        <svg width="36" height="36" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M4.5 27V24H31.5V27H4.5ZM4.5 19.5V16.5H31.5V19.5H4.5ZM4.5 12V9H31.5V12H4.5Z"
                                fill="white" />
                        </svg>
                    </a>
                    <ul class="header-links header-links_mobile" :class="{ 'active': isMenuOpen, '': !isMenuOpen }">
                        <li class="header-links__item" v-for="link in links" :key="link">
                            <a href="javascript:void(0);" class="header-lnks__link">{{ link }}</a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>

    </header>
</template>
<style>
.header-top {
    font-family: Roboto, sans-serif;
    width: 100%;
    align-items: center;
    color: #000;

    * {
        color: #000;
    }

}

.header-top-wrapper {
    display: flex;
    justify-content: space-between;
    padding: 20px 0 22px 0;
    margin: 0 auto;
    width: 1440px;
    max-width: 100%;

    & span,
    a {
        font-size: 16px;
        line-height: 19px;
    }
}

.header-bottom {
    font-family: inter, sans-serif;
    font-weight: 700;
    background-color: #547966;
}

.header-bottom-wrapper {
    display: grid;
    align-items: center;
    grid-template-columns: 68px 1fr;
    column-gap: 68px;
    padding: 15px 0;
    margin: 0 auto;
    width: 1440px;
    max-width: 100%;
}

.logo {
    display: flex;
    align-items: center;
    justify-content: center;
}

.header-links {
    display: flex;
    align-items: center;
    justify-content: space-between;
    column-gap: 12px;
    row-gap: 12px;
    margin: 0;
    padding: 0;
    list-style: none;

    .header-links__item {
        * {
            font-size: 18px;
            line-height: 21px;
            text-decoration: none;
            color: #fff;
        }

        *:hover {
            color: #8FFFC6;
        }
    }
}

.link {
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
}

.link.link_phone {
    display: flex;
    justify-content: center;
    column-gap: 13px;
}

.mobile-menu-wrapper {
    display: none;
}

@media(max-width:1440px) {

    .header-bottom-wrapper,
    .header-top-wrapper {
        padding: 15px 20px;
    }

}

@media(max-width:1280px) {
    .header-bottom-wrapper {
        column-gap: 20px;
    }

    .header-links {
        & .header-links__item {
            * {
                font-size: 15px;
                line-height: 18px;
                text-decoration: none;
                color: #fff;
            }
        }
    }
}

@media(max-width:956px) {
    .header-top-wrapper {

        & span {
            font-size: 12px;
            line-height: 14px;
            text-align: left
        }
    }

    .link.link_phone{
        width: 100%;
        justify-content: flex-end;
    }


    .header-links {
        display: none;
    }

    .header-links.header-links_mobile {
        position: absolute;
        flex-direction: column;
        min-height: calc(100vh - 122px);
        justify-content: normal;
        align-items: flex-end;
        top: 100%;
        left: 0;
        right: 0;
        width: 100%;
        background-color: #547966;
        padding: 15px 20px;
    }

    .header-links.header-links_mobile.active {
        display: flex;
        z-index: 2;
    }

    .header-bottom-wrapper {
        position: relative;
        display: flex;
        justify-content: space-between;
    }

    .mobile-menu-wrapper {
        display: flex;
        align-items: center;
        justify-content: center;
    }
}
</style>
<script>
export default {
    name: 'HeaderComponent',
    data() {
        return {
            isMenuOpen: false,
            links: [
                'Classic Brokerage MT4 | MT5',
                'Margin World Class Exchange',
                'Crypto World Class Exchange',
                'Financial Licensing'
            ]
        };
    },
    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen;
        }
    }
}
</script>