<template>
  <p style="font-family: 'Times New Roman', Times, serif; color: palevioletred">
    Cat<span>Nap</span>
  </p>

  <div class="container">
    <div class="cat">
      <div class="head">
        <div class="ears">
          <div></div>
          <div></div>
        </div>
        <div class="face">
          <div class="eyes">
            <div></div>
            <div></div>
          </div>

          <div class="nose">
            <div class="mustache">
              <div></div>
              <div></div>
              <div></div>
            </div>
            <div class="mustache">
              <div></div>
              <div></div>
              <div></div>
            </div>
          </div>
        </div>
      </div>
      <div class="body">
        <div class="tail"></div>
      </div>

      <div class="sleep">
        <div>z</div>
        <div>z</div>
        <div>z</div>
        <div>z</div>
        <div>z</div>
        <div>z</div>
      </div>
    </div>
  </div>
  <div class="bg"></div>
</template>

<script setup></script>

<style lang="scss" scoped>
$bg: #344661;
$greyBase: #fff;
$greyDark: #525252;

@mixin alignFlex() {
  display: flex;
  align-items: center;
  justify-content: center;
}

* {
  box-sizing: border-box;
}

body {
  height: 100%;
  width: 100%;
  background: $bg;
  overflow: hidden;
  margin: 0;
}
p {
  padding: 24px;
  margin: 0;
  position: absolute;
  color: darken($greyBase, 15%);
  font-size: 2.4rem;
  font-family: "Assistant";
  top: 0;
}
p span {
  color: darken($greyBase, 35%);
}
.container {
  position: absolute;
  left: calc(50% - 63px);
  top: 50%;
  transform: translate(-50%, -50%);
  @include alignFlex();
}

.cat {
  width: 115px;
  height: 220px;
}

.head {
  background: $greyBase;
  width: 114px;
  height: 100px;
  border-radius: 141% 98% 55% 189%;
  position: absolute;
  top: 15px;
  transform: translateY(10px);
  z-index: 25;
  animation: sleep 4s ease-out infinite;
}

@keyframes sleep {
  0% {
    transform: translateY(10px);
  }

  50% {
    transform: translateY(0px);
  }

  100% {
    transform: translateY(10px);
  }
}

.ears {
  & > div:nth-child(1),
  & > div:nth-child(2) {
    height: 20px;
    width: 2px;
    position: absolute;
    left: 64px;
    top: -28px;
    border-bottom: 40px solid $greyBase;
    border-left: 30px solid transparent;
    border-right: 7px solid transparent;
    border-top: 0px solid transparent;
    -webkit-transform-origin: bottom;
    transform-origin: bottom;
    -webkit-transform: rotate(-5deg);
    transform: rotate(-5deg);
    border-radius: 14px 46px 0px 28px;

    &:before {
      content: "";
      height: 15px;
      width: 0px;
      position: absolute;
      border-bottom: 22px solid $greyDark;
      border-left: 8px solid transparent;
      border-right: 2px solid transparent;
      left: -11px;
      top: 5px;
      transform: rotate(10deg);
    }
  }

  & > div:nth-child(2) {
    height: 20px;
    width: 2px;
    position: absolute;
    left: 10px;
    top: -32px;
    border-bottom: 40px solid $greyBase;
    border-left: 30px solid transparent;
    border-right: 7px solid transparent;
    border-top: 0px solid transparent;
    -webkit-transform-origin: bottom;
    transform-origin: bottom;
    -webkit-transform: rotate(-22deg);
    transform: rotate(-22deg);
    border-radius: 0px 34px 3px 0;
  }
}

.sleep {
  & > div {
    position: absolute;
    bottom: 140px;
    left: 40px;
    font-size: 1.8rem;
    color: $greyDark;
    z-index: -1;
    transition: all 1s ease-out;
  }
  @for $i from 1 to 3 {
    & > div:nth-child(#{$i}) {
      transform: translate(10px, 10px);
      animation: zzz 5s $i * 3s ease-in-out infinite;
      left: ($i * 20) + px;
    }
  }
  @for $i from 4 to 6 {
    & > div:nth-child(#{$i}) {
      transform: translate(10px, 10px);
      animation: zzz 4.5s $i * 2s ease-in-out infinite;
    }
  }
}

@keyframes zzz {
  0% {
    transform: translate(10px, 10px);
    opacity: 1;
  }
  100% {
    transform: translate(10px, -240px);
    opacity: 0;
  }
}

.face {
  display: flex;
  height: 100%;
  align-items: center;
  padding-top: 25px;
  height: 93%;
  flex-direction: column;
  position: relative;
  z-index: 1;
}

.eyes {
  display: flex;
  justify-content: space-evenly;
  width: 100%;
  & > div {
    height: 20px;
    width: 20px;
    background: $greyBase;
    box-shadow: inset 3px 4px $greyDark;
    border-radius: 68% 6%;
    transform: rotate(219deg);
  }
}

.nose {
  width: 100%;
  display: flex;
  flex-direction: column;
  display: flex;
  align-items: center;
  justify-content: center;

  &:before {
    content: "";
    height: 0px;
    width: 0px;
    border-top: 6px solid $greyDark;
    border-left: 6px solid transparent;
    border-right: 6px solid transparent;
    border-bottom: 0px solid transparent;
    margin-top: 4px;
    display: inline-block;
  }
}

.mustache {
  width: 100%;
  position: absolute;

  & > div {
    height: 12px;
    width: 3px;
    background: $greyDark;
    transform: rotate(90deg);
  }
}

.nose > div:nth-child(2) {
  transform: translateX(111px);
}

.body {
  background: $greyBase;
  width: 236px;
  height: 120px;
  border-radius: 237% 242% 196% 216%;
  position: absolute;
  top: 51px;
}

.tail {
  width: 85px;
  height: 120px;
  position: absolute;
  left: 100px;
  top: 44%;
  border-radius: 200px;
  box-shadow: inset 10px 34px 0px $greyBase;
  transform: rotate(-451deg);

  &:after {
    content: "";
    position: absolute;
    width: 124px;
    height: 94px;
    border-radius: 0 0 264px 218px;
    top: 57%;
    box-shadow: inset 10px -10px $greyBase;
  }
}

.bg {
  background: #415675;
  width: 100%;
  height: 50vh;
}
</style>
