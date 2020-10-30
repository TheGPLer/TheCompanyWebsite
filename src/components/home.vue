<template>
  <el-container>
    <el-header>
      <el-menu
          :default-active="activeIndex"
          class="el-menu-home"
          mode="horizontal"
          @select="handleSelect"
          background-color="#fff"
          text-color="#000"
          active-text-color="#E40C1A">
        <el-menu-item index="1">首页</el-menu-item>
        <el-submenu index="2">
          <template slot="title">关于我们</template>
          <el-menu-item index="2-1">公司概览</el-menu-item>
          <el-menu-item index="2-2">公司荣誉</el-menu-item>
          <el-menu-item index="2-3">管理团队</el-menu-item>
          <el-menu-item index="2-4">发展历程</el-menu-item>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title">联系我们</template>
          <el-menu-item index="3-1">联系我们</el-menu-item>
          <el-menu-item index="3-2">加入我们</el-menu-item>
        </el-submenu>
      </el-menu>
    </el-header>
    <el-main>
      <!-- 轮播图 -->
      <div class="block">
        <el-carousel trigger="click" height="458px">
          <el-carousel-item v-for="item in items" :key="item.id">
            <img :src="item.src">
          </el-carousel-item>
        </el-carousel>
      </div>
      <div class="block media">
        <div class="line"></div>
        <div class="title">媒体信息</div>
        <div class="line"></div>
        <div style="height: 200px;text-align: left;padding: 40px;">
          此处省略 1K 字。（还没做完）
        </div>
      </div>
    </el-main>
    <el-footer>
      <div class="bottom_nav">
        <div style="width: 1200px;margin: 0 auto;">
          <div style="float: left;margin-top: 33px">
            <div style="margin-bottom: 35px;font-size: 16px">联系我们</div>
            <div style="float:left;margin-right: 63px;font-size: 13px">
              <div style="margin-bottom: 13px">
                <span>TEL: xxx-xxxx</span>
              </div>
              <div style="margin-bottom: 13px">
                <span>xxx@xx.xxx</span>
              </div>
            </div>
            <div style="float:left;margin-right: 63px;font-size: 13px">
              <div style="margin-bottom: 13px">
                <span>company.gpler.ml</span>
              </div>
              <div style="margin-bottom: 13px">
                <span>XX市XX号</span>
              </div>
            </div>
          </div>
          <div style="float: right;margin-top: 33px;margin-left: 40px">
            <img src="../assets/logo.png" style="height: 100px;width: 100px;vertical-align: middle;border: none" />
            <div style="font-size: 14px;color: #fff;margin-top: 14px;width: 100px;text-align: center;">Vue.js</div>
          </div>
          <div style="float: right;margin-top: 33px;margin-left: 40px">
            <img src="../assets/logo.png" style="height: 100px;width: 100px;vertical-align: middle;border: none" />
            <div style="font-size: 14px;color: #fff;margin-top: 14px;width: 100px;text-align: center;">Vue.js</div>
          </div>
        </div>
      </div>
      <div class="bottom_bar">
        Copyright©2018-2020 XX有限公司 版权所有 浙ICP备XX号
      </div>
    </el-footer>
  </el-container>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      activeIndex: "1",
      items: [
        {
          id: 1,
          src: 'https://cdn.oss.youkua.net/official/image/202001/20/f02ef892-c44b-4c9b-aecb-f26730f36d46.png'
        },
        {
          id: 2,
          src: 'https://cdn.oss.youkua.net/official/image/202001/20/76f97c05-17e9-4445-9ae1-b90a2e80730d.png'
        }
      ]
    }
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath)
      let str = ''
      switch (key) {
        case "1": str = '首页';break;
        case "2-1": str = '关于我们-公司概览';break;
        case "2-2": str = '关于我们-公司荣誉';break;
        case "2-3": str = '关于我们-管理团队';break;
        case "2-4": str = '关于我们-发展历程';break;
        case "3-1": str = '联系我们-联系我们';break;
        case "3-2": str = '联系我们-加入历程';break;
      }
      const h = this.$createElement;
      this.$notify({
        title: '提示',
        message: h('i', {style: 'color: teal'}, str + '被点击')
      });
    }
  }
}
</script>

<style scoped>

.el-menu-home {
  display: flex;
  padding-left: 1%;
  padding-right: 1%;
}
.el-menu-home > .el-menu-item {
  margin-right: auto;
}
.media {
  text-align: center;
  align-items: center;
  justify-content: center;
  padding-top: 50px;
}
.title {
  font-size: 27px;
  font-weight: bold;
  color: #E40C1A;
  padding-left: 20px;
  padding-right: 20px;
  vertical-align: middle;
  display: inline-block;
}
.line {
  width: 60px;
  height: 2px;
  background: #E40C1A;
  display: inline-block;
}

.bottom_nav {
  height: 200px;
  width: 100%;
  color: white;
  background: #8F010C;
  min-width: 1200px;
}

.bottom_bar {
  margin: 0 auto;
  text-align: center;
  color: white;
  background: #6F0006;
  height: 34px;
  line-height: 34px;
  min-width: 1200px;
}

.el-footer {
  padding: 0;
}
.el-main {
  padding: 0;
}
.el-header {
  padding: 0;
}
</style>
