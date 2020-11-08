<template>
  <a
    href="javascript:;"
    class="menu-item"
    title="点我加载更多"
    @mouseenter="isOpen = true"
    @mouseleave="isOpen = false"
    >{{ title }}
    <!-- 下拉箭头图片 -->
    <svg
      class="down"
      id="headerDown"
      viewBox="0 0 32 32"
      width="100%"
      height="100%"
    >
      <path
        d="M15.992 25.304c-0 0-0 0-0.001 0-0.516 0-0.981-0.216-1.31-0.563l-0.001-0.001-14.187-14.996c-0.306-0.323-0.494-0.76-0.494-1.241 0-0.998 0.809-1.807 1.807-1.807 0.517 0 0.983 0.217 1.313 0.565l0.001 0.001 12.875 13.612 12.886-13.612c0.331-0.348 0.797-0.565 1.314-0.565 0.481 0 0.918 0.187 1.242 0.493l-0.001-0.001c0.723 0.687 0.755 1.832 0.072 2.555l-14.201 14.996c-0.33 0.348-0.795 0.564-1.311 0.564-0.001 0-0.003 0-0.004 0h0z"
      ></path>
    </svg>
    <transition name="fade">
      <div class="sub-menu" v-if="isOpen">
        <!-- 设置三角图标 -->
        <i></i>
        <a
          :href="item.link"
          class="menu-item sub-item"
          v-for="(item, i) in subMenuDatas"
          :key="i"
          >{{ item.title }}</a
        >
      </div>
    </transition>
  </a>
</template>
<script>
//import  from "";
// const  =()=>import("components/common/footer/Footer")
export default {
  name: "",
  props: {
    title: {
      type: String,
      default() {
        return "更多";
      },
    },
    subMenuDatas: {
      type: Array,
      default() {
        return [
          { title: "选项1", link: "#" },
          { title: "选项2", link: "#" },
          { title: "选项3", link: "#" },
        ];
      },
    },
  },
  data() {
    return {
      isOpen: false,
    };
  },
  computed: {
    setStyle() {
      return {};
    },
  },
  components: {},
};
</script>
<style>
.fade-enter-active,
.fade-leave-active {
  transition: all 0.15s ease-in;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.menu-item.active,
.menu-item:hover {
  background-color: #0366d6;
}
.menu-item {
  position: relative;
  display: block;
  /* border: 3px solid transparent; */
  box-sizing: border-box;
  height: 64px;
  line-height: 64px;
  padding: 0 15px;
  color: #fff;
  background-color: #24292e;
  text-decoration: none;
  transition: all 0.2s;
  font-size: 14px;
}

.menu-item svg {
  margin: 0;
  padding: 0;
  width: 10px;
  height: 10px;
  fill: #ffffff;
}
.menu-item .sub-menu {
  position: relative;
  margin: 0;
  padding: 0;
  position: absolute;
  background-color: pink;
  color: #3d454d;
  width: max-content;
  top: calc(100% + 3px);
  left: 50%;
  transform: translateX(-50%);
  box-shadow: 0 0 1px 1px rgba(0, 0, 0, 0.1);
}
.menu-item .sub-menu .sub-item.active,
.menu-item .sub-menu .sub-item:hover {
  background-color: #e6f0fb;
}
.menu-item .sub-menu .sub-item {
  color: #3d454d;
  background-color: #fff;
}
.menu-item .sub-menu i {
  position: absolute;
  border: 10px solid transparent;
  border-bottom-color: #fff;
  z-index: 999;
  left: 50%;
  transform: translateX(-50%);
  top: -20px;
  /* border-sh; */
}
</style>