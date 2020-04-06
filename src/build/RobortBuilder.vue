<template>
        <div>
          <div class="top-row">
            <div class="top part">
              <img v-bind:src="availableParts.heads[selectHeadIndex].src"  title="head"/>
              <button v-on:click="selectprevHead" class="prev-selector">&#9668;</button>
              <button v-on:click="selectNextHead" class="next-selector">&#9658;</button>
            </div> 
          </div>
          <div class="middle-row">
            <div class="left part">
               <img v-bind:src="availableParts.arms[selectArmIndex].src">
              <button v-on:click="selectprevLeftArm" class="prev-selector">&#9650;</button>
              <button v-on:click="selectNextrightArm"  class="next-selector">&#9655;</button>
            </div>
            <div class="center part">
             <img v-bind:src="availableParts.torsos[selectTorqueIndex].src">
              <button @click="selectLeftTorque" class="prev-selector">&#9668;</button>
              <button @click="selectRightTorque" class="next-selector">&#9658;</button>
            </div>
            <div class="right part">
               <img v-bind:src="availableParts.arms[selectRightArmIndex].src">
              <button @click="selectNextrightTopArm" class="prev-selector">&#9650;</button>
              <button @click="selectNextrightBottomArm" class="next-selector">&#9660;</button>
            </div>
          </div>
          <div class="bottom-row">
            <div class="bottom part">
               <img v-bind:src="availableParts.bases[selectBaseIndex].src">
              <button @click="selectLeftBase" class="prev-selector">&#9668;</button>
              <button  @click="selectRightBase" class="next-selector">&#9658;</button>
            </div>
          </div>
      </div>
</template>



<script>
import availableParts from '../data/parts';

function getPreviousValidIndex (index, length) {
    const deprecatedIndex = index -1;
   return deprecatedIndex < 0 ? length - 1 : deprecatedIndex; 
}


function getNextValidIndex(index, length) {
    const incrementIndex = index +1;
    return incrementIndex > length - 1 ? 0 : incrementIndex;
}



export default {
    name:'RobortBuilder',
    data() {
        return {
           availableParts,
           selectHeadIndex: 0,
           selectArmIndex: 0,
           selectRightArmIndex:0,
           selectTorqueIndex:0,
           selectBaseIndex:0,
        }
    },
    methods : {
        selectNextHead(){
            this.selectHeadIndex = 
            getNextValidIndex(
                this.selectHeadIndex,
                availableParts.heads.length,
            )
        },
        selectprevHead(){
            this.selectHeadIndex = 
            getPreviousValidIndex(
                this.selectHeadIndex,
                availableParts.heads.length,
            )
        },
       selectprevLeftArm(){
            this.selectArmIndex = 
            getPreviousValidIndex(
                this.selectArmIndex,
                availableParts.arms.length,
            )
        },
        
        selectNextrightArm(){
            this.selectArmIndex = 
            getNextValidIndex(
                this.selectArmIndex,
                availableParts.arms.length,
            )
        },
        
        selectNextrightTopArm() {
            this.selectRightArmIndex = 
            getPreviousValidIndex(
                this.selectRightArmIndex,
                availableParts.arms.length,
            )
        },
        
        selectNextrightBottomArm() {
            this.selectRightArmIndex = 
            getNextValidIndex(
                this.selectRightArmIndex,
                availableParts.arms.length,
            )
        },
        
        selectLeftTorque() {
            this.selectTorqueIndex = 
            getPreviousValidIndex(
                this.selectTorqueIndex,
                availableParts.torsos.length
            )
        },
        selectRightTorque() {
            this.selectTorqueIndex = 
            getNextValidIndex(
                this.selectTorqueIndex,
                availableParts.torsos.length
            )
        },
        
        
        selectLeftBase() {
            this.selectBaseIndex = 
            getPreviousValidIndex(
                this.selectBaseIndex,
                availableParts.torsos.length
            )
        },
        
        
        selectRightBase() {
            this.selectBaseIndex = 
            getNextValidIndex(
                this.selectBaseIndex,
                availableParts.torsos.length
            )
        },
    }
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