<!--
 * @Name: 文件用途
 * @Copyright: 广州银云信息科技有限公司
 * @Author: 
 * @Date: 2022-03-06 18:40:39
 * @LastEditors: qintian
 * @LastEditTime: 2022-03-06 21:32:08
-->
<template>
<div class="f_row_ac nav-box" >
  <div class=" f_row_ac navbar fg1">
    <img class="navbar_img" src="../../assets/huaban/huaban.png">
    <div class="navbar_find cp">发现</div>
    <div class="navbar_search fg1">
      <div class="navbar_search_font">搜索</div>
      <span class="navbar_search_box ">
        <span class="iconfont fs20 mr5 icon-sousuo "></span>
        <input autocomplete="off" type="text" class="navbar_search_input">
      </span>
    </div>
    <span class="img_box cp"><img class="ml20 img" src="../../assets/huaban/jiudian.png"></span>
      <button class="login_button">登录/注册</button>
  </div>
</div>
</template>

<script >

</script>

<style lang="scss" >
  .nav-box {
    color: #fff;
    min-width: 1060px;
    margin: 0 auto;
    padding: 0 24px;
    border-bottom: 1px solid #ebebeb;
    .search-box {
      position: relative;
      .icons {
        position: absolute;
        right: 4px;
        top: 5px;
        color: #aaa;
        width: 18px;
        text-align: center;
        height: 18px;
        font-size: 17px;
        user-select: none;
        border-radius: 3px;
        border: 1px solid #616163;
        background-color: #45454e;
      }
      .eo-input {
        width: 200px;

        &::-webkit-input-placeholder {
          color: #999;
        }

        &:focus {
          border-color: transparent !important;
        }

        &.show-input {
          color: #fff;
          background-color: #2b2b37;
          border-color: #494951;
        }
      }
    }

    .btn-register {
      padding: 5px 10px;
      border-radius: 3px;
      border: 1px solid #fff;
    }

    .nav-item {
      padding: 10px 15px;
      cursor: pointer;
    }
  }
  .navbar {
    color: #333;
    font-weight: bold;
    font-size: 16px;
    height: 80px;
    .navbar_img {
      width: 32px;
      height: 32px;
      background-repeat: no-repeat;
      background-size: 100% 100%;
    }
    .img_box {
      padding: 8px 8px;
      margin-right: 4px;
      .img {
        width: 18px;
        height: 18px;
      }
    }
    .navbar_find {
      padding: 0 0 0 24px;
    }
    .navbar_search {
      input {
        border: none;
        outline: none;
        width: 100%;
      }
      font-weight: 600;
      font-size: 16px;
      position: relative;
      margin: 0 22px;
      width: auto;
      .navbar_search_font {
        position: absolute;
        left: 51px;
        z-index: 2;
        top: 50%;
        margin-top: -11px;
        color: rgba(30, 32, 35, 0.3);
        pointer-events: none;
      }
      .navbar_search_box {
        height: 48px;
        border-radius: 24px;
        padding: 0 3px 0 24px;
        color: #8a8e91;
        font-weight: 600;
        font-size: 16px;
        width: 100%;
        background-color: #edf2f5;
        border-color: transparent;
        display: flex;
        align-items: center;
      }
      .navbar_search_input {
        margin: 0;
        position: relative;
        display: inline-block;
        width: 100%;
        min-width: 0;
        font-size: 14px;
        line-height: 1.5715;
        overflow: visible;
        background-color: #edf2f5;
      }
    }
    .login_button {
      border-radius: 20px;
      border: 1px solid #1e2023;
      width: 94px;
      height: 40px;
      font-size: 14px;
      color: #1e2023;
      font-variant: tabular-nums;
      line-height: 1.5715;
    }
    .login_button:hover{
      color: #ff5967;
      border-color: #ff5967;
    }
  }
</style>
