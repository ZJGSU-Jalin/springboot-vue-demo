<template>
  <div style="padding: 10px">
<!--    功能-->
    <div style="margin: 10px 0; color: lightyellow">
      <el-button type="primary">新增</el-button>
      <el-button type="primary">导入</el-button>
      <el-button type="primary">导出</el-button>
    </div>
<!--    搜索-->
    <div style="margin: 10px 0">
      <el-input v-model="search" placeholder="请输入关键字" style="width: 20%"></el-input>
      <el-button type="primary" style="margin-left: 5px">查询</el-button>
    </div>
    <el-table :data="tableData" border stripe style="width: 100%">
      <el-table-column prop="date" label="日期" width="180" sortable> </el-table-column>
      <el-table-column prop="name" label="姓名" width="180" sortable> </el-table-column>
      <el-table-column prop="address" label="地址" sortable> </el-table-column>
      <el-table-column label="操作" width="100">
        <template #default="scope">
          <el-button @click="handleEdit(scope.row)" type="text" size="small">编辑</el-button>
          <el-popconfirm title="确定删除吗？">
            <template #reference>
              <el-button type="text" size="small">删除</el-button>
            </template>
          </el-popconfirm>
        </template>
      </el-table-column>
    </el-table>
    <div style="margin: 10px 0">
      <el-pagination
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
          :current-page="currentPage"
          :page-sizes="[5, 10, 20]"
          :page-size="10"
          layout="total, sizes, prev, pager, next, jumper"
          :total="total"
      >
      </el-pagination>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {

  },
  data() {
    return {
      search: '',
      currentPage: 1,
      total: 10,
      tableData: [
        {
          date: '2016-05-02',
          name: 'aaa',
          address: '上海市普陀区金沙江路 1518 弄',
        },
        {
          date: '2016-05-04',
          name: 'bbb',
          address: '上海市普陀区金沙江路 1517 弄',
        },
        {
          date: '2016-05-01',
          name: 'ccc',
          address: '上海市普陀区金沙江路 1519 弄',
        },
        {
          date: '2016-05-03',
          name: 'ddd',
          address: '上海市普陀区金沙江路 1516 弄',
        },
        {
          date: '2016-05-03',
          name: 'eee',
          address: '上海市普陀区金沙江路 1516 弄',
        },
        {
          date: '2016-05-03',
          name: 'fff',
          address: '上海市普陀区金沙江路 1516 弄',
        },

      ],
      method: {
        handleEdit() {

        },
        handleSizeChange() {

        }
      }
    }
  }
}
</script>
