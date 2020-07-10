<template>
  <el-dialog
    :visible="visible"
    v-on:update:visible="updateFormDialogVisible"
    :title="title"
    width="80%"
    :close-on-click-modal="false"
  >
    <div>
      此处可进行表单表格内容补充。。。。。
    </div>
    <div slot="footer" class="dialog-footer" style="text-align:center;">
      <el-button
        type="primary"
        size="small"
        >确认</el-button
      >
      <el-button
        type="danger"
        size="small"
        >返回</el-button
      >
    </div>
  </el-dialog>
</template>

<script>
export default {
  name: "dialog",
  components: {  },
  data() {
    return {
      
      
    };
  },
  props: {
    visible: Boolean,
    title: String,
    data: Array
  },
  computed: {
    
  },
  watch: {
    
  },
  methods: {
    // 更新弹出框显示状态
    updateFormDialogVisible() {
      this.$emit("update:visible", false);//false代表关闭弹框
    },
  },
};
</script>

<style scoped></style>
