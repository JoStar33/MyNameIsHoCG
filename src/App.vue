<template>
    <v-app>
        <main class="sticky-container" ref="sticky-container">
            <div class="firstScreen">
                <h1><span>"WELCOME&nbsp;</span></h1><h1><span>&nbsp;TO&nbsp;</span><span>&nbsp;HoCG!"</span></h1>
            </div>
            <div class="sticky">
                <div class="slide-container">
                    <div class="slide" ref="sl1">
                        <div class="slide-big-text">
                            <MainView/>
                        </div>
                    </div>
                    <div class="scdown" ref="scdown">
                        <div class="scdown-text">
                        </div>
                    </div>
                    <div class="slide" ref="sl2">
                        <div class="slide-big-text">
                            <p>저의 다양한 컨텐츠 제작 능력들을 소개해드리죠.</p>
                            <StackText/>
                        </div>
                    </div>
                    <div class="slide sl3" ref="sl3">
                        <div class="slide-big-text">
                            <p>
                                동쪽에서 새로운 해가
                            </p>
                            <p>이윽고 떠올랐습니다.</p>
                        </div>
                    </div>
                    <div class="slide slide-left sl4" ref="sl4">
                        <div class="sl4-content">
                            <div class="slide-big-text" ref="sl4-big">
                                <p ref="sl4-big-1">자세한</p>
                                <p ref="sl4-big-2">설명이</p>
                                <p ref="sl4-big-3">있을 수도 있어요</p>
                            </div>
                            <div class="slide-small-text">
                                <p>
                                    그렇습니다.
                                </p>
                                <p>
                                    이건
                                </p>
                                <p>
                                    글씨가 좀 작습니다.
                                </p>
                            </div>
                        </div>
                    </div>
                    <div class="wave" ref="wave">
                        뭔가 독립적으로 움직이는 배경
                    </div>

                    <div class="slide slide-left sl5" ref="sl5">
                        <div class="slide-big-text">
                            <p>엘바노프 스튜디오는</p>
                            <p>당신의 풍요로운</p>
                            <p>나날을 꿈꿉니다.</p>
                        </div>
                        <div class="go-surf-wrapper">
                            <a href="https://elvanov.com/2195" target="_blank">이 코드의 설명을 보려면 여기를 눌르세요.</a>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </v-app>
</template>

<script>
    //npm install bezier-easing
    import MainView from './views/MainView.vue';
    import StackText from './components/StackText.vue';
    import bezierEasing from "bezier-easing";

    const ease = bezierEasing(0.25, 0.1, 0.25, 1.0);
    const easeIn = bezierEasing(0.38, 0.01, 0.78, 0.13);
    const midSlow = bezierEasing(0, 0.7, 1, 0.3);

    const def = {
        height: 7100,
        elements: {
            sl1: {
                top: 500,
                bottom: 1900,
                topStyle: {
                    opacity: 0,
                    translateY: -60
                },
                bottomStyle: {
                    opacity: 0,
                    translateY: 60
                }
            },
            scdown: {
                top: 0,
                bottom: 1000,
                topStyle: {
                    opacity: 1
                },
                bottomStyle: {
                    opacity: 0
                }
            },
            sl2: {
                top: 1900,
                bottom: 3200,
                topStyle: {
                    opacity: 0,
                    translateY: -60
                },
                bottomStyle: {
                    opacity: 0,
                    translateY: 60
                }
            },
            sl3: {
                top: 3300,
                bottom: 4600,
                topStyle: {
                    opacity: 0
                },
                bottomStyle: {
                    opacity: 0
                }
            },
            wave: {
                top: 4500,
                bottom: 5900,
                topStyle: {
                    opacity: 0,
                    translateY: 300
                },
                bottomStyle: {
                    opacity: 0,
                    translateY: 0
                }
            },
            sl4: {
                top: 4700,
                bottom: 6000,
                topStyle: {
                    opacity: 0
                },
                bottomStyle: {
                    opacity: 0
                }
            },
            sl5: {
                top: 6100,
                bottom: 9000,
                topStyle: {
                    opacity: 0
                },
                bottomStyle: {
                    opacity: 0
                }
            }
        },
        animations: {
            sl1: [
                {
                    top: 500,
                    bottom: 1900,
                    easing: midSlow,
                    styles: {
                        translateY: {
                            topValue: 60,
                            bottomValue: -60
                        }
                    }
                }, {
                    top: 500,
                    bottom: 800,
                    easing: ease,
                    styles: {
                        opacity: {
                            topValue: 0,
                            bottomValue: 1
                        }
                    }
                }, {
                    top: 1400,
                    bottom: 1900,
                    easing: easeIn,
                    styles: {
                        opacity: {
                            topValue: 1,
                            bottomValue: 0
                        }
                    }
                }
            ],
            scdown: [
                {
                    top: 600,
                    bottom: 1000,
                    easing: easeIn,
                    styles: {
                        opacity: {
                            topValue: 1,
                            bottomValue: 0
                        }
                    }
                }
            ],
            sl2: [
                {
                    top: 1900,
                    bottom: 3200,
                    easing: midSlow,
                    styles: {
                        translateY: {
                            topValue: 60,
                            bottomValue: -60
                        }
                    }
                }, {
                    top: 1900,
                    bottom: 2500,
                    easing: ease,
                    styles: {
                        opacity: {
                            topValue: 0,
                            bottomValue: 1
                        }
                    }
                }, {
                    top: 2600,
                    bottom: 3200,
                    easing: easeIn,
                    styles: {
                        opacity: {
                            topValue: 1,
                            bottomValue: 0
                        }
                    }
                }
            ],
            sl3: [
                {
                    top: 3300,
                    bottom: 4600,
                    easing: midSlow,
                    styles: {
                        translateY: {
                            topValue: 60,
                            bottomValue: -60
                        }
                    }
                }, {
                    top: 3300,
                    bottom: 3900,
                    easing: ease,
                    styles: {
                        opacity: {
                            topValue: 0,
                            bottomValue: 1
                        }
                    }
                }, {
                    top: 4000,
                    bottom: 4600,
                    easing: easeIn,
                    styles: {
                        opacity: {
                            topValue: 1,
                            bottomValue: 0
                        }
                    }
                }
            ],
            wave: [
                {
                    top: 4500,
                    bottom: 5300,
                    easing: ease,
                    styles: {
                        translateY: {
                            topValue: 200,
                            bottomValue: 0
                        },
                        opacity: {
                            topValue: 0,
                            bottomValue: 1
                        }
                    }
                }, {
                    top: 5300,
                    bottom: 5900,
                    easing: easeIn,
                    styles: {
                        opacity: {
                            topValue: 1,
                            bottomValue: 0
                        }
                    }
                }
            ],
            sl4: [
                {
                    top: 4700,
                    bottom: 6000,
                    easing: midSlow,
                    styles: {
                        translateY: {
                            topValue: 60,
                            bottomValue: -60
                        }
                    }
                }, {
                    top: 4700,
                    bottom: 5300,
                    easing: ease,
                    styles: {
                        opacity: {
                            topValue: 0,
                            bottomValue: 1
                        }
                    }
                }, {
                    top: 5400,
                    bottom: 6000,
                    easing: easeIn,
                    styles: {
                        opacity: {
                            topValue: 1,
                            bottomValue: 0
                        }
                    }
                }
            ],
            sl5: [
                {
                    top: 6100,
                    bottom: 7100,
                    easing: midSlow,
                    styles: {
                        translateY: {
                            topValue: 60,
                            bottomValue: -60
                        }
                    }
                }, {
                    top: 6100,
                    bottom: 6700,
                    easing: ease,
                    styles: {
                        opacity: {
                            topValue: 0,
                            bottomValue: 1
                        }
                    }
                }
            ]
        }
    };

    let enabled = new Map();
    let disabled = new Map();

    const isAmong = (num, top, bottom) => num >= top && num <= bottom;

    const applyStyle = (element, styleName, value, unit = "px") => {
        if (styleName === "translateY") {
            // eslint-disable-next-line no-param-reassign
            element.style.transform = `translateY(${value}${unit})`;
            return;
        }
        if (styleName === "translateX") {
            // eslint-disable-next-line no-param-reassign
            element.style.transform = `translateX(${value}${unit})`;
            return;
        }
        // eslint-disable-next-line no-param-reassign
        element.style[styleName] = value;
    };

    export default {      
        components: {
            MainView,
            StackText
        },
        mounted() {
            this.init();
            window.addEventListener("scroll", this.onScroll);
        },
        beforeDestroy() {
            window.removeEventListener("scroll", this.onScroll);
        },

        methods: {
            init() {
                this.initAnimation();
            },
            // 애니메이션 초기화
            initAnimation() {
                // Sticky Conainer 의 높이를 설정함.
                this
                    .$refs["sticky-container"]
                    .style
                    .height = `${def.height}px`;

                // disabled, enabled 를 비움.
                disabled.clear();
                enabled.clear();

                // 모든 요소를 disabled 에 넣음.
                for (const refname of Object.keys(def.elements)) {
                    disabled.set(refname, def.elements[refname]);
                }

                // 각 애니메이션을 enabled == false 로 만듬.
                for (const refname of Object.keys(def.animations)) {
                    for (const animation of def.animations[refname]) {
                        animation.enabled = false;
                    }
                }

                // 초기 스타일 적용
                disabled.forEach((obj, refname) => {
                    Object
                        .keys(obj.topStyle)
                        .forEach((styleName) => {
                            const pushValue = obj.topStyle[styleName];
                            this
                                .$refs[refname]
                                .style[styleName] = pushValue;
                        });
                });

                // 이미 요소의 범위 및 애니메이션의 범위에 있는 것들을 렌더링하기 위해 임의로 스크롤 이벤트 핸들러를 한 번 실행시킴.
                this.onScroll();
            },
            applyStyles(currentPos, refname, styles, r, unit = "px") {
                for (const style of Object.keys(styles)) {
                    const {topValue, bottomValue} = styles[style];
                    const calc = (bottomValue - topValue) * r + topValue;
                    applyStyle(this.$refs[refname], style, calc, unit);
                }
            },
            applyAllAnimation(currentPos, refname) {
                const animations = def.animations[refname];
                if (!animations) 
                    return;
                for (const animation of animations) {
                    const {top: a_top, bottom: a_bottom, easing, styles} = animation;
                    const isIn = isAmong(currentPos, a_top, a_bottom);
                    // 만약 애니메이션이 새롭게 들어갈 때 혹은 나갈때 enabled 설정
                    if (isIn) {
                        if (!animation.enabled) 
                            animation.enabled = true;
                        }
                    else if (!isIn && animation.enabled) {
                        if (currentPos <= a_top) {
                            this.applyStyles(currentPos, refname, styles, 0);
                        } else if (currentPos >= a_bottom) {
                            this.applyStyles(currentPos, refname, styles, 1);
                        }
                        // eslint-disable-next-line no-param-reassign
                        animation.enabled = false;
                    }

                    // 애니메이션이 enabled 라면, 애니메이션 적용.
                    if (animation.enabled) {
                        const r = easing((currentPos - a_top) / (a_bottom - a_top));
                        // eslint-disable-next-line no-param-reassign
                        this.applyStyles(currentPos, refname, styles, r);
                    }
                }
            },
            onScroll() {
                // 현재 스크롤 위치 파악
                const scrollTop = window.scrollY || window.pageYOffset;
                const currentPos = scrollTop + window.innerHeight / 2;

                // disabled 순회하며 활성화할 요소 찾기.
                disabled.forEach((obj, refname) => {
                    // 만약 칸에 있다면 해당 요소 활성화
                    if (isAmong(currentPos, obj.top, obj.bottom)) {
                        enabled.set(refname, obj);
                        this
                            .$refs[refname]
                            .classList
                            .remove("disabled");
                        this
                            .$refs[refname]
                            .classList
                            .add("enabled");
                        disabled.delete(refname);
                    }
                });

                // enabled 순회하면서 헤제할 요소를 체크
                enabled.forEach((obj, refname) => {
                    const {top, bottom, topStyle, bottomStyle} = obj;
                    // console.log(`${top}, ${bottom}, ${topStyle}, ${bottomStyle}`); 범위 밖에 있다면
                    if (!isAmong(currentPos, top, bottom)) {
                        // 위로 나갔다면 시작하는 스타일 적용
                        if (currentPos <= top) {
                            Object
                                .keys(topStyle)
                                .forEach((styleName) => {
                                    applyStyle(this.$refs[refname], styleName, topStyle[styleName]);
                                }// 아래로 나갔다면 끝나는 스타일적용);
                              );
                        } else if (currentPos >= bottom) {
                            Object
                                .keys(bottomStyle)
                                .forEach((styleName) => {
                                    applyStyle(this.$refs[refname], styleName, bottomStyle[styleName]);
                                    // this.$refs[refname].style[styleName] = bottomStyle[styleName];
                                });
                        }
                        // 리스트에서 삭제하고 disabled로 옮김.
                        disabled.set(refname, obj);
                        this
                            .$refs[refname]
                            .classList
                            .remove("enabled");
                        this
                            .$refs[refname]
                            .classList
                            .add("disabled");
                        enabled.delete(refname// enable 순회중, 범위 내부에 제대로 있다면 각 애니메이션 적용시키기.
                        );
                    } else {
                        this.applyAllAnimation(currentPos, refname);
                    }
                });
            }
        }
    }
</script>

<style lang="scss" > 
@import url("https://fonts.googleapis.com/css?family=Luckiest+Guy&display=swap");

.firstScreen {
  background: radial-gradient(
    circle,
    //rgba(255, 252, 0, 1) 0%,
    //rgba(240, 237, 23, 1) 100%
  );
  height: 500px;
}

.firstScreen {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Luckiest Guy", cursive;
}

.firstScreen > h1 {
  margin: 0;
  font-size: 8em;
  padding: 0;
  color: white;
  text-shadow: 0 0.1em 20px rgba(0, 0, 0, 1), 0.05em -0.03em 0 rgba(0, 0, 0, 1),
    0.05em 0.005em 0 rgba(0, 0, 0, 1), 0em 0.08em 0 rgba(0, 0, 0, 1),
    0.05em 0.08em 0 rgba(0, 0, 0, 1), 0px -0.03em 0 rgba(0, 0, 0, 1),
    -0.03em -0.03em 0 rgba(0, 0, 0, 1), -0.03em 0.08em 0 rgba(0, 0, 0, 1), -0.03em 0 0 rgba(0, 0, 0, 1);
  .firstScreen > span {
    transform: scale(0.9);
    display: inline-block;
  }
  .firstScreen > span:first-child {
    animation: bop 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards infinite
      alternate;
  }
  .firstScreen > span:last-child {
    animation: bopB 1s 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards
      infinite alternate;
  }
}

@keyframes bop {
  0% {
    transform: scale(0.9);
  }
  50%,
  100% {
    transform: scale(1);
  }
}

@keyframes bopB {
  0% {
    transform: scale(0.9);
  }
  80%,
  100% {
    transform: scale(1) rotateZ(-3deg);
  }
}
//이 아래부터는 길게 자연스럽게 나아가는 html 구조를 위한 scss
body {
    padding: 0;
    margin: 0;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
}

.c2 {
    height: 400px;
}

.sticky {
    position: sticky;
    top: 0;
    width: 100%;
    height: 100vh;
}

.slide-container {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
}
.slide {
    position: absolute;
    display: none;
    z-index: 0;
}
.slide.enabled {
    display: block;
}

.slide-big-text p {
    margin: 0;
    font-size: 45px;
    font-weight: bold;
    line-height: 1.35;
    letter-spacing: -1.5px;
    word-spacing: 1.5px;
    text-align: center;
}

.slide-small-text {
    margin-top: 20px;
    margin-left: 5px;
}

.slide-small-text p {
    font-size: 18px;
    margin: 0;
}

.scdown {
    position: absolute;
    padding: 30px 0;
    width: 100%;
    height: 50px;
    text-align: center;
    bottom: 0;
}
</style>
