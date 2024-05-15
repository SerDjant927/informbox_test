<template>
    <main class="main">
        <div v-if="slides.length" class="slider">
            <div class="slides" :style="{ transform: `translateX(${currentTranslate}px)` }" ref="slides">
                <div v-for="(slide, index) in slides" :key="index" class="slide"
                    :class="{ active: currentIndex === index }" v-html="slide">
                </div>
            </div>
            <div class="dots">
                <span v-for="(slide, index) in slides" :key="index" class="dot"
                    :class="{ active: currentIndex === index }" @click="goToSlide(index)"></span>
            </div>
        </div>
    </main>
</template>

<script>
export default {
    name: 'ContentComponent',
    data() {
        return {
            slides: [
                `<div class="slide-item">
                    <div>
                        <h3>Margin World Class Exchange</h3>
                        <span>"Become a world class broker by the most innovative tranding platform in the sector. 
                            <br/>
                            <br/>
Overpass traditional technologies and offer your clients FX, Crypto, CFD, Commodities, ETF, Stocks along with the most innovative tools, trading view charts, multiple nominee accounts, dynamic leverage, adaptable widgets.
                            <br/>
                            <br/>
Trading has never been as simple and professional as now.</span>
                    <button>Now it work</button>
                    </div>
                    <div>
                        <picture>
                            <source srcset="img/small1.png" media="(min-width: 600px)" />
                            <img src="img/big1.png" alt="MDN" />
                        </picture>
                    </div>
                </div>`,
                `<div class="slide-item">
                    <div>
                        <h3>Financial Licensing</h3>
                        <span>"Get Licensed from two weeks on and start your brokerage business now. 
                            <br/>
                            <br/>
Brokerage Business and Spot Crypto Exchange are two of the most important branches in the financial sector. In order to receive financial instruments from liquidity providers, to offer trading services and payment facilities, your Brokerage Business or exchange is needed to be licensed.
<br/>
                            <br/>
Amazon Brokers guides you through different jurisdictions, assisting you on the best legal framework for your Brokerage Business model. "</span>
<button>Now it work</button>
                    </div>
                    <div>
                        <picture>
                            <source srcset="img/small2.png" media="(min-width: 600px)" />
                            <img src="img/big2.png" alt="MDN" />
                        </picture>
                    </div>
                </div>`,
                `<div class="slide-item">
                    <div>
                        <h3>Crypto World Class Exchange</h3>
                        <span>Amazon brokers, offers a broad range of resources to launch your own branded Exchange
                            <br/>
                            <br/>
A turkey operation based upon a custom matching engine for better contol and scalability
                            <br/>
                            <br/>
Time-cost effective turnkey service powerd by the robust Trading  Machine Engine </span>
<button>Now it work</button>
                    </div>
                    <div>
                        <picture>
                            <source srcset="img/small4.png" media="(min-width: 600px)" />
                            <img src="img/big4.png" alt="MDN" />
                        </picture>
                    </div>
                </div>`
            ],
            currentIndex: 0,
            startX: 0,
            currentTranslate: 0
        };
    },
    mounted() {
        this.$refs.slides.addEventListener('touchstart', this.touchStart);
        this.$refs.slides.addEventListener('touchmove', this.touchMove);
        this.$refs.slides.addEventListener('touchend', this.touchEnd);
    },
    methods: {
        goToSlide(index) {
            this.currentIndex = index;
            this.currentTranslate = -index * this.$refs.slides.offsetWidth;
        },
        touchStart(event) {
            this.startX = event.touches[0].clientX;
        },
        touchMove(event) {
            const touchX = event.touches[0].clientX;
            const diffX = touchX - this.startX;
            this.currentTranslate = -this.currentIndex * this.$refs.slides.offsetWidth + diffX;
        },
        touchEnd(event) {
            const touchX = event.changedTouches[0].clientX;
            const diffX = touchX - this.startX;
            if (Math.abs(diffX) > 50) {
                if (diffX > 0 && this.currentIndex > 0) {
                    this.currentIndex--;
                } else if (diffX < 0 && this.currentIndex < this.slides.length - 1) {
                    this.currentIndex++;
                }
            }
            this.currentTranslate = -this.currentIndex * this.$refs.slides.offsetWidth;
        }
    }
};
</script>

<style>

.main{
    display: flex;
    width: 1440px;
    max-width: 100%;
    margin: 120px auto ;
}

.slider {
    position: relative;
    overflow: hidden;
}

.slides {
    display: flex;
    transition: transform 0.3s ease;
}

.slide {
    transition: all 1.5s;
    flex: 0 0 100%;
    opacity: 0;
}

.slide.active {
    transition: all 1.5s;
    opacity: 1;
}

.slide-item {
    display: grid;
    grid-template-columns: 1fr 1fr;
    div{
        h3{
            margin: 0 0 20px;
            font-family: inter, sans-sarif;
            font-weight: 700;
            color: #000;
            font-size: 64px;
            line-height: 70px;
            text-align: left
        }
        span{
            display: flex;
            font-family: inter,sans-serif;
            font-weight: 400;
            font-size: 20px;
            line-height: 30px;
            letter-spacing: 7%;
            color:#3f3f3f;
            width: 496px;
            max-width: 100%;
            text-align: left;
        }
        button{
            margin-top: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: Roboto, sans-serif;
            font-weight: 700;
            font-size: 16px;
            line-height: 45px;
            color:#fff;
            padding: 0 34px;
            border-radius: 10px;
            background-color: #547966;
            border: none;
        }
        button:hover{
                background-color: #5EB086;
            }
    }
}

.dots {
    display: flex;
    justify-content: center;
    margin-top: 10px;
}

.dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: gray;
    margin: 0 5px;
    cursor: pointer;
}

.dot.active {
    background-color: black;
}

.slide-item {}

img {
    max-width: 100%;
    overflow: hidden;
}

@media(max-width:768px){
    .main{
        margin-top: 34px;
    }
    .slide-item{
        grid-template-columns: 1fr;
        padding: 0 20px;
    }
    .slide-item {
    & div {
        h3{
            font-size: 32px;
            line-height: 42px;
        }
        span{
            width:100%;
            font-size: 16px;
            line-height: 20px;
        }
    }
}
        
}

@media(max-width:600px) {
    img {
        max-width: 100%;
        overflow: hidden;
    }
}
</style>
