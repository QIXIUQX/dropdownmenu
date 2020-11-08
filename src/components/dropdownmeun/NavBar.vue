<template>
  <!-- 使用flex 布局   -->
  <nav>
    <!-- 点击弹出下拉框 再次点击收起 -->
    <DropDownMenu title="更多" :subMenuDatas="subMenuDatas" />
    <DropDownMenu title="默认数据" />
  </nav>
</template>
<script>
//import  from "";
// const  =()=>import("components/common/footer/Footer")
const DropDownMenu = () => import("./DropDownMenu");
export default {
  name: "",
  data() {
    return {
      // 测试数据
      subMenuDatas: [
        { title: "百度", link: "http://www.baidu.com" },
        { title: "微博", link: "https://weibo.com/" },
      ],
    };
  },
  components: { DropDownMenu },
};
</script>
<style>
nav {
  display: flex;
  height: 64px;
  width: 100%;
}
</style>