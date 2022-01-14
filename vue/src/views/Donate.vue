<template>
  <div style="padding: 10px">
    <el-row :gutter="20">
      <el-col :span="12">
        <el-card>
          <div style="padding: 10px 0; font-size: 18px">如果您在使用过程中有任何疑问，请联系我们</div>
          <el-image style="width: 240px" :src="wx" :preview-src-list="[wx]"></el-image>
          <el-image style="width: 240px; margin-left: 100px" :src="alipay" :preview-src-list="[alipay]"></el-image>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "Donate",
  data() {
    return {
      wx: "https://img-blog.csdnimg.cn/92fa3dccbec54a69bb0e73d398fecf54.jpg?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAd2F0ZXIgdGhyZWU=,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center",
      alipay: 'https://img-blog.csdnimg.cn/92fa3dccbec54a69bb0e73d398fecf54.jpg?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAd2F0ZXIgdGhyZWU=,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center'
    }
  }
}
</script>

<style scoped>

</style>
