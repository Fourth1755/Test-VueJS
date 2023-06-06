<template>
  <div class="aselect" :data-value="value" :data-list="list">
    <div class="selector" @click="toggle()">
      <div class="label">
        <span>{{ value }}</span>
      </div>
      <div class="arrow" :class="{ expanded: visible }"></div>
      <div :class="{ hidden: !visible, visible }">
        <ul>
          <li
            :class="{ current: item === value }"
            v-for="(item,index) in list"
            :key="index"
            @click="select(item)"
          >
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SelectBoxDrpodown",
  data(){
    return{
        value: 'Select a Country',
        visible: false
    }
  },
  props:["list"],
  methods:{
    toggle() {
		this.visible = !this.visible;
	},
	select(option) {
		this.value = option;
	}
  }
};
</script>

<style lang="scss" scoped>
    .aselect {
        width: 220px;
        margin: 20px auto;
        .selector {
            border: 1px solid #000;
            background: #2D3033;
            position: relative;
            z-index: 1;
            .arrow {
                position: absolute;
                right: 10px;
                top: 40%;
                width: 0;
                height: 0;
                border-left: 7px solid transparent;
                border-right: 7px solid transparent;
                border-top: 10px solid #888;
                transform: rotateZ(0deg) translateY(0px);
                transition-duration: 0.6s;
                transition-timing-function: cubic-bezier(0.59, 1.39, 0.37, 1.01);
            }
            .expanded {
                transform: rotateZ(180deg) translateY(2px);
            }
            .label {
                display: block;
                padding: 10px;
                font-size: 16px;
                color: #eaeaea;
            }
        }
        ul {
            width: 100%;
            list-style-type: none;
            padding: 0;
            margin: 0;
            font-size: 16px;
            border: 1px solid #000;
            position: absolute;
            z-index: 1;
            background: #2D3033;
        }
        li {
            padding: 12px;
            color: #666;
            &:hover {
            color: white;
            background: #F37832;
            }
        }
        .current {
            background: #eaeaea;
        }
        .hidden {
            visibility: hidden;
        }
        .visible {
            visibility: visible;
        }
    }
</style>