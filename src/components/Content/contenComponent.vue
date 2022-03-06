<!--
 * @Name: 文件用途
 * @Copyright: 广州银云信息科技有限公司
 * @Author: 
 * @Date: 2022-03-06 18:40:39
 * @LastEditors: qintian
 * @LastEditTime: 2022-03-07 01:39:11
-->
<template>
  <div class="content_box">
    <div class="select_box f_row_ac po_re">
      <div class="left_select f_row_ac po_ab">
        <div
          class="left_select_word cp"
          v-bind:class="{ bg_grey: select == 1 }"
          v-on:click="Fnselect('collect')"
        >
          采集
        </div>
        <div
          class="left_select_word cp"
          v-bind:class="{ bg_grey: select == 2 }"
          v-on:click="Fnselect('broad')"
        >
          画板
        </div>
      </div>
      <div
        class="right_select f_row_ac"
        v-bind:class="{ spreed: spreed == 1, shrink: spreed == 2 }"
      >
        <div
          class="right_select_word"
          v-for="(item, i) in selectArr"
          v-bind:class="{ click: clickItem == i && !item.icon }"
          v-on:click="item.icon ? '' : (clickItem = i)"
        >
          <span v-if="!item.icon">{{ item }}</span>
          <span
            v-if="item.icon == 1"
            class="iconfont icon-jiantou_yemian_xiangxia_o"
            v-on:click="FnchangeMenu('spreed')"
          ></span>
          <span
            v-if="item.icon == 2"
            class="iconfont icon-jiantou_yemian_xiangshang"
            v-on:click="FnchangeMenu('shrink')"
          ></span>
        </div>
      </div>
    </div>
    <div class="picture_box" id="content">
      <div class="picture_box_item cp" v-for="item in imgArr">
        <!-- <div class="f_row_ac hover_box">
          <div class="hover_box_collection f_row_ac">
            <button class="collect_button_left"><span>采集</span></button>
            <button class="collect_button_right cp">
              <span class="iconfont icon-shanguangdeng fs20"></span>
            </button>
          </div>
          <div class="hover_box_favarite">
            <button class="cp">
              <span class="iconfont icon-xiai_o"></span>
            </button>
          </div>
        </div>-->
        <img :src="item" />
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
import picture from './picture.js'
export default {
  data() {
    return {
      spreed: null,
      clickItem: 0,
      select: 1,
      imgArr: picture,
      selectArr: [
        '最新',
        'UI/UX',
        '平面',
        '插画/漫画',
        '摄影',
        '游戏',
        '动漫',
        '工业设计',
        '建筑设计',
        { icon: 1 },
        '人文设计',
        '家居/家装',
        '女装/搭配',
        '男士/风尚',
        '造型/美妆',
        '手工/布艺',
        '美食',
        '旅行',
        '婚礼',
        '儿童',
        '宠物',
        '美图',
        '明星',
        '美女',
        '礼物',
        '极客',
        '数据图',
        '汽车/摩托',
        '电影/图书',
        '生活百科',
        '教育',
        '运动',
        '搞笑',
        { icon: 2 },
      ],
    }
  },
  methods: {
    initData() {
      console.log('sdasdsad')
    },
    Fnselect: function (input) {
      if (input == 'collect') {
        this.select = 1
      } else {
        this.select = 2
      }
    },
    FnchangeMenu: function (input) {
      if (input == 'spreed') {
        this.spreed = 1
        this.selectArr[9].icon = 3
      } else {
        this.spreed = 2
        this.selectArr[9].icon = 1
      }
    },
  },
  mounted: function () {
    const fnSort = () => {
      let content = document.getElementById('content'),
        contentWidth = content.offsetWidth
      let imgs = content.children,
        imgsWidth = imgs[0].offsetWidth,
        nums = Math.floor(contentWidth / imgsWidth),
        arrHeight = []
      for (var i = 0; i < imgs.length; i++) {
        if (i < nums) {
          arrHeight.push(imgs[i].offsetHeight)
        } else {
          var obj = {
            minH: arrHeight[0],
            minI: 0,
          }
          for (var j = 0; j < arrHeight.length; j++) {
            if (arrHeight[j] < obj.minH) {
              obj.minH = arrHeight[j]
              obj.minI = j
            }
          }
          imgs[i].style.position = 'absolute'
          imgs[i].style.left = imgs[obj.minI].offsetLeft + 'px'
          imgs[i].style.top = obj.minH + 20 + 'px'
          arrHeight[obj.minI] = arrHeight[obj.minI] + 20 + imgs[i].offsetHeight
        }
      }
    }
       setTimeout(() => {
        fnSort()
      }, 500)
  },
}
</script>

<style lang="scss" src="./index.scss"></style>
