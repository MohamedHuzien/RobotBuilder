<template>
      <div>
    <div class="top-row">
      <div class="top part">
        <img v-bind:src="parts.heads[headIndex].src" title="head"/>
        <button v-on:click="getPrevious(boxType.head.type)" class="prev-selector">&#9668;</button>
        <button v-on:click="getNext(boxType.head.type)" class="next-selector">&#9658;</button>
      </div>
    </div>
    <div class="middle-row">
      <div class="left part">
        <img v-bind:src="parts.arms[leftArmIndex].src" title="left arm"/>
        <button v-on:click="getPrevious(boxType.leftArm.type)" class="prev-selector">&#9650;</button>
        <button v-on:click="getNext(boxType.leftArm.type)" class="next-selector">&#9660;</button>
      </div>
      <div class="center part">
        <img v-bind:src="parts.torsos[torsosIndex].src" title="torsos"/>
        <button v-on:click="getPrevious(boxType.torsos.type)" class="prev-selector">&#9668;</button>
        <button v-on:click="getNext(boxType.torsos.type)"  class="next-selector">&#9658;</button>
      </div>
      <div class="right part">
        <img v-bind:src="parts.arms[rightArmIndex].src" title="right arm"/>
        <button v-on:click="getPrevious(boxType.rightArm.type)" class="prev-selector">&#9650;</button>
        <button v-on:click="getNext(boxType.rightArm.type)"  class="next-selector">&#9660;</button>
      </div>
    </div>
    <div class="bottom-row">
      <div class="bottom part">
        <img v-bind:src="parts.bases[baseIndex].src" title="bases arm"/>
        <button v-on:click="getPrevious(boxType.bases.type)" class="prev-selector">&#9668;</button>
        <button v-on:click="getNext(boxType.bases.type)" class="next-selector">&#9658;</button>
      </div>
    </div>
  </div>
</template>

<script>
import {parts, boxType } from '../data/parts.js';
export default {
    name : "RobotBuilder",
    data() {
      return {
        parts,
        boxType,
        headIndex:0,
        leftArmIndex : 0,
        rightArmIndex : 0,
        torsosIndex : 0,
        baseIndex : 0

      }
    },
    methods: {
      getNext(boxtype) {
        if(this.boxType.head.type == boxtype) {
        (this.headIndex + 1 == this.parts.heads.length) ? this.headIndex = 0 : this.headIndex++;
        }else if(this.boxType.leftArm.type == boxtype) {
          (this.leftArmIndex + 1 == this.parts.arms.length) ? this.leftArmIndex = 0 : this.leftArmIndex++;
        }else if(this.boxType.rightArm.type == boxtype) {
          (this.rightArmIndex + 1 == this.parts.arms.length) ? this.rightArmIndex = 0 : this.rightArmIndex++;
        }else if(this.boxType.torsos.type == boxtype) {
          (this.torsosIndex + 1 == this.parts.torsos.length) ? this.torsosIndex = 0 : this.torsosIndex++;
        }else if(this.boxType.bases.type == boxtype) {
          (this.baseIndex + 1 == this.parts.bases.length) ? this.baseIndex = 0 : this.baseIndex++;
        }

    },
      getPrevious(boxtype) {
        if(this.boxType.head.type == boxtype) {
        (this.headIndex - 1 < 0) ? this.headIndex = this.parts.heads.length - 1 : this.headIndex--;
        }else if(this.boxType.leftArm.type == boxtype) {
          (this.leftArmIndex - 1 < 0) ? this.leftArmIndex = this.parts.arms.length - 1 : this.leftArmIndex--;
        }else if(this.boxType.rightArm.type == boxtype) {
          (this.rightArmIndex - 1 < 0) ? this.rightArmIndex = this.parts.arms.length - 1 : this.rightArmIndex--;
        }else if(this.boxType.torsos.type == boxtype) {
          (this.torsosIndex - 1 < 0) ? this.torsosIndex = this.parts.torsos.length - 1 : this.torsosIndex--;
        }else if(this.boxType.bases.type == boxtype) {
          (this.baseIndex - 1 < 0) ? this.baseIndex = this.parts.bases.length - 1 : this.baseIndex--;
        }
      } 
    },
}
</script>

<style>
.part {
  position: relative;
  width:165px;
  height:165px;
  border: 3px solid #aaa;
} 
.part img {
  width:165px;
}
.top-row {
  display:flex;
  justify-content: space-around;
}
.middle-row {
  display:flex;
  justify-content: center;
}
.bottom-row {
  display:flex;
  justify-content: space-around;
  border-top: none;
}
.head {
  border-bottom: none;
}
.left {
  border-right: none;
}
.right {
  border-left: none;
}
.left img {
  transform: rotate(-90deg);
}
.right img {
  transform: rotate(90deg);
}
.bottom {
  border-top: none;
}
.prev-selector {
  position: absolute;
  z-index:1;
  top: -3px;
  left: -28px;
  width: 25px;
  height: 171px;
}
.next-selector {
  position: absolute;
  z-index:1;
  top: -3px;
  right: -28px;
  width: 25px;
  height: 171px;
}
.center .prev-selector, .center .next-selector {
  opacity:0.8;
}
.left .prev-selector {
  top: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}
.left .next-selector {
  top: auto;
  bottom: -28px;
  left: -3px;    
  width: 144px;
  height: 25px;
}
.right .prev-selector {
  top: -28px;
  left: 24px;  
  width: 144px;
  height: 25px;
}
.right .next-selector {
  top: auto;
  bottom: -28px;
  left: 24px;    
  width: 144px;
  height: 25px;
}
.right .next-selector {
  right: -3px;
}
</style>
