<template>
  <div class="print-container">
    <h1 style="text-align: center">员工信息表</h1>
    <el-table
        :data="tableData"
        style="width: 100%"
        border>
      <el-table-column
          prop="date"
          label="日期"
          width="180">
      </el-table-column>
      <el-table-column
          prop="name"
          label="姓名"
          width="180">
      </el-table-column>
      <el-table-column
          prop="gender"
          label="性别"
          width="100">
      </el-table-column>
      <el-table-column
          prop="address"
          label="地址">
      </el-table-column>
      <el-table-column
          prop="phone"
          label="手机">
      </el-table-column>
    </el-table>
    <div class="print-button-container">
      <el-button type="primary" icon="el-icon-printer" @click="handlePrint">打印</el-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Print',
  props: {
    msg: String
  },
  data() {
    return {
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        gender: '男',
        address: '上海市普陀区金沙江路 1518 弄',
        phone: '19029384851'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        gender: '男',
        address: '上海市普陀区金沙江路 1517 弄',
        phone: '19029384851'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        gender: '男',
        address: '上海市普陀区金沙江路 1519 弄',
        phone: '19029384851'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        gender: '男',
        address: '上海市普陀区金沙江路 1516 弄',
        phone: '19029384851'
      }]
    }
  },

  methods: {
    /**
     * 调用浏览器的打印方法
     */
    handlePrint() {
      window.print()
    }
  }
}
</script>
<style>
@media print {
  @page {
    /* 纵向打印 */
    size: portrait;

    /* 横向打印 */
    /*size: landscape;*/

    /* 去掉页眉页脚*/
    margin-top: 0;
    margin-bottom: 0;
  }

  /*打印不显示打印按钮*/
  .print-button-container {
    display: none !important;
  }
}
</style>
<style scoped>
.print-container {
  width: 1000px;
  margin: 0 auto;
}

.print-button-container {
  display: flex;
  justify-content: flex-end;
  margin-top: 15px;
}

/*字体调黑*/
>>> .el-table {
  font-size: 16px;
  color: #000000;
}

>>> .el-table th {
  font-weight: normal;
  font-size: 18px;
}

>>> .el-table thead {
  color: #000000;
}

/*边框调黑*/
>>> .el-table::before {
  background-color: #000000;
}

>>> .el-table--border::after {
  background-color: #000000;
}

>>> .el-table--border th, >>> .el-table--border td {
  border-color: #000000;
}

>>> .el-table--group, >>> .el-table--border {
  border-color: #000000;
}

>>> .el-table th.is-leaf, >>> .el-table td {
  border-bottom: 1px solid #000000;
}

/*减小单元格间距*/
>>> .el-table th, >>> .el-table td {
  padding: 0 0;
}

/*显示底部边框 估计打印时伪元素把border覆盖了 height设为0隐藏伪元素*/
>>> .el-table::before {
  height: 0;
}

/*显示右边框*/
>>> .el-table--group::after, >>> .el-table--border::after {
  width: 0;
}
</style>
