<template>
  <div class="app-container customerMgt">
    <div class="search-box"></div>
    <el-table
      v-loading="listLoading"
      @selection-change="getSelection"
      :data="dataList"
      border
      fit
      size="mini"
    >
      <el-table-column align="center" type="selection" width="55" :selectable="checkboxT" />
      <el-table-column label="序号" type="index" show-overflow-tooltip width="50">
        <template slot-scope="scope">
          <span>
            {{
            (postData.pageNum - 1) * postData.pageSize + scope.$index + 1
            }}
          </span>
        </template>
      </el-table-column>
    </el-table>
    <Pagination
      :total="postData.total"
      :page.sync="postData.pageNum"
      :limit.sync="postData.pageSize"
      @pagination="getDataList"
    ></Pagination>

    <dialog title="弹框" :visible.sync="dialogVisible" :data="processData" v-if="dialogVisible"></dialog>
    <!-- 延期按钮(计划延期新增) -->
  </div>
</template>

<script>
import dialog from "./dialog";

export default {
  name: "table-page",
  components: {},
  data() {
    return {
      dataList: [],
      dialogVisible: false,
      processData: [],
      // 查询条件
      postData: {
        pageNum: 1,
        pageSize: 10,
        total: 0
      }
    };
  },
  methods: {
    openDialog() {
      // 此处可对要传递弹框内容进行绑定
      this.processData = [{ name: "xxx", age: "xxx" }];
      this.dialogVisible = true;
    },
    //分页结果完成回调函数
    getDataList(){
      // 请求数据
      // this.dataList = res.data;
      // this.postData.total = res.data.total;
    }
  }
  // 弹框
};
</script>

<style lang="scss"></style>
