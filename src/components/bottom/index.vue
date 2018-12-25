<template>
  <div class="bottom-wrapper">
    <div class="desc">
      <i class="iconfont icon-warning-circle"></i>
      <div class="content">
        <span class="word">票面价</span>是指通过景区指定窗口售卖的纸质门票上标注的价格
      </div>
    </div>
    <ul class="icon-list">
      <li class="item"><span class="air"></span><span class="word">机票</span></li>
      <li class="item"><span class="hotel"></span><span class="word">酒店</span></li>
      <li class="item"><span class="house"></span><span class="word">公寓</span></li>
      <li class="item more"><img class="more-img" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAYCAYAAADkgu3FAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAIfSURBVEhLvVbnysJAEMz7P4u9otgbKIogKvaCvbcH2I8JXLi77BlR+H4oanI7szOzG63X60X/8bJkkPF4TN1u9yfgx+NBjUaDDoeDUscBGg6H5Pf7yefzUbPZ/ArscrlQNpu1a8TjcTqdTk4dG6jf79sX5Ve1WiWw+1TW/X5PiURCqZFMJgngqGHdbjcbXQfC91wuR7juBbZcLikcDrM10IQNhDegZjIZ9sZUKqVIoIMOBgMKBAKus/htNBqp0uEwZKrVaixYLBaj3W7n6qzdbrP3R6NRWq/XfBgE006n44RCljMUChEkEqTgISd3Op1mFVDiLcCm0ykFg0FWDmhukrlcLtP9fmc9ZYEAuN1ujSHhOoGM70JjBPIKiQBD5xh0r2QqQPP5XEmKV0hg+mazUUCezyehO3lYnXjjA3wRMUUgdIZ6SGD6+XxW7sPMFQoF21t5WB0g5F2sHyEJ9hXYyYCz2YyQvkql4jIdHWDmZP9ARgy8db1eCRJwBpdKJbag3i3kM9UQS9r26Hg8utgIYEQZZExmm0YBCvV6PfdmQIvFYpHtDHqDjA4GtrrkIIi9t1gszJsBnrRaLeNaEQnDffV63UgKm1wnxc4Rnk3cosTMTCYTJ1m6r/l83iizcWBXqxVFIhGWNRccLqVyV283w7uQCDB4JJ45X68gHMSSRMy5LjjTTWBvOxKHuJAgifofkJ86kg+LkMD0Tx7x8tk/qrabQu3SN6AAAAAASUVORK5CYII=" alt=""><span class="word">更多</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'BottomCom'
}
</script>

<style lang="less" scoped>
.bottom-wrapper {
  display: flex;
  flex-flow: column nowrap;
  .desc {
    display: flex;
    flex-flow: row nowrap;
    background-color: #fff;
    padding: 7px;
    i {
      color: rgb(97, 97, 97);
      padding: 0 5px;
    }
    .content {
      text-align: left;
      line-height: 16px;
      .word {
        font-weight: 700;
      }
    }
  }
  .icon-list {
    display: flex;
    flex-flow: row nowrap;
    padding: 10px 0 5px 0;
    line-height: 25px;
    justify-content: space-around;
    color: rgb(172, 172, 172);
    .item {
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      position: relative;
      .air {
        display: inline-block;
        width: 22px;
        height: 22px;
        background: url(http://source.qunarzz.com/site/images/wap/touch/images/v2/images2x/nav_7.png) 0 0;
        background-size: 175px 50px;
        margin-right: 5px;
      }
      .hotel {
        display: inline-block;
        width: 22px;
        height: 22px;
        background: url(http://source.qunarzz.com/site/images/wap/touch/images/v2/images2x/nav_7.png) 0 0;
        background-size: 175px 50px;
        margin-right: 5px;
        background-position: -25px 0;
      }
      .house {
        display: inline-block;
        width: 22px;
        height: 22px;
        background: url(http://source.qunarzz.com/site/images/wap/touch/images/v2/images2x/nav_7.png) 0 0;
        background-size: 175px 50px;
        margin-right: 5px;
        background-position: -150px 0;
      }
      &.more {
        padding: 5px 0 5px 30px;
        &:before {
          content: '';
          position: absolute;
          left: 0;
          top: 0;
          width: 1px;
          height: 100%;
          background-color: rgb(172, 172, 172);
          transform: scaleY(0.5)
        }
       .more-img {
        width: 12px;
        height: 12px;
      }
      }
      .word {
        text-decoration: underline;
      }
    }
  }
}
</style>
