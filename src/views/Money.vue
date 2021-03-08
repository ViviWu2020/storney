<template>
  <layout class-prefix="layout">
    <div class="numberPad">
      <div class="output">100</div>
      <div class="button">
        <button>1</button>
        <button>2</button>
        <button>3</button>
        <button>删除</button>
        <button>4</button>
        <button>5</button>
        <button>6</button>
        <button>清空</button>
        <button>7</button>
        <button>8</button>
        <button>9</button>
        <button class="OK">OK</button>
        <button class="zero">0</button>
        <button>.</button>
      </div>
    </div>
    <div>
      <ul class="types">
        <li class="selected">支出</li>
        <li>收入</li>
      </ul>
    </div>
    <div>
      <label class="notes">
        <span class="name">备注</span>
      <input type="text" placeholder="在这里输入备注">
      </label>
    </div>
    <div class="tags">
      <div class="new">
        <button>新增标签</button>
      </div>
      <ul class="current">
        <li>衣</li>
        <li>食</li>
        <li>住</li>
        <li>行</li>
      </ul>
    </div>
  </layout>
</template>

<script lang="ts">
export default {
  name: 'Money',
};
</script>

<style lang="scss">
  .layout-content{
    display: flex;
    flex-direction: column-reverse;
  }

</style>
<style lang="scss" scoped>
  @import "~@/assets/style/helper.scss";
  .tags {
    flex-grow: 1;
    font-size: 14px;
    padding: 16px;
    display: flex;
    flex-direction: column-reverse;
    > .current{
      display: flex;
      flex-wrap: wrap;
      overflow: auto;
      > li{
        background: #D8FFA8;
        height: 24px;
        line-height: 24px;
        border-radius: 12px;
        padding: 0 14px;
        margin-right: 12px;
        margin-top: 4px;
      }
    }
    > .new{
      padding-top: 16px;
      button{
        background: transparent;
        border: none;
        border-bottom: 1px solid;
        color: #999;
        padding: 0 4px;
      };
    }
  }

  .notes{
    font-size: 14px;
    display: flex;
    align-items: center;
    background: #E9FDE4;
    padding-left: 16px ;

    .name{
       padding-right: 16px;
    }
    input{
      height: 62px;
      flex-grow: 1;
      background: transparent;
      border: none;
      padding-right: 16px;
    }
  }

  .types{
    background: #178852;
    display: flex;
    text-align: center;
    font-size: 24px;
    > li{
      width: 50%;
      height: 64px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      &.selected{
        &::after{
          content: '';
          position: absolute;
          bottom: 0;
          left: 0;
          width: 100%;
          height: 4px;
          background: #333333;
        }
      }
    }
  }

  .numberPad{
    .output{
      @extend %clearFix;
      @extend %innerShadow;
      font-size: 36px;
      font-family: Consolas, monospace;
      padding: 9px 16px;
      text-align: right;
    }
    .button{
      @extend %clearFix;
      > button{
        width: 25%;
        height: 64px;
        float: left;
        background: transparent;
        border: none;
        &.OK{
          height: 64*2px;
          float: right;
        }
        &.zero{
          width: 25*2%;
        }
        &:nth-child(1){
          background: #D8FFA8;
        }
        &:nth-child(2),&:nth-child(5){
          background: #C0FF9D;
        }
        &:nth-child(3),&:nth-child(6),&:nth-child(9){
          background: #97F888;
        }
        &:nth-child(4),&:nth-child(7), &:nth-child(10){
          background: #69F586;
        }
        &:nth-child(8),&:nth-child(11), &:nth-child(13){
          background: #42E273;
        }
        &:nth-child(14){
          background: #29B662;
        }
        &:nth-child(12){
          background: #178852;
        }
      }
    }
  }

</style>