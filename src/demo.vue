<template>
  <div class="t-demo__style">
    <!-- row-class-name 设置行类名 -->
    <t-table
      row-key="index"
      :data="data"
      :columns="columns"
      :row-class-name="changeRowClass"
      id="111"
      :rowAttributes="[{ color: 'yellow' }]"
      >å
    </t-table>
  </div>
</template>

<script lang="jsx">
const data = [];
const total = 5;
for (let i = 0; i < total; i++) {
  data.push({
    index: i,
    applicant: ['贾明', '张三', '王芳'][i % 3],
    status: i,
    color: ['#ff0011', '#ff0122', '#ff1033'][i % 3],
  });
}
export default {
  data() {
    return {
      data,
      columns: [
        { colKey: 'applicant', title: '申请人', width: 100 },
        {
          colKey: 'status',
          title: '审批状态',
          width: 120,
        },
        {
          colKey: 'color',
          title: '行颜色',
          width: 120,
        },
      ],
    };
  },

  methods: {
    changeRowClass(params) {
      // let style = document.createElement('style');
      // style.backgroundColor = 'yellow';
      // document.getElementsByTagName('head')[0].appendChild(style);

      if (params.rowIndex >= 1) return 'custom-third-class-name';
      return 'custom-third-classall';
    },
  },
};
</script>

<style>
.t-demo__style .t-table .custom-third-class-name > td {
  color: green;
  font-weight: bold;
}

.t-demo__style .t-table .custom-third-classall > td {
  color: green;
  font-weight: bold;
  background-color: pink;
}

.t-demo__style .t-table td.last-column-class-name {
  color: orange;
  font-weight: bold;
}

.t-table td.custom-cell-class-name {
  color: orange;
  font-size: 18px;
  font-weight: bold;
  background-color: red;
}

.t-table td.custom-cell-class-name22 {
  color: orange;
  font-size: 18px;
  font-weight: bold;
  background-color: blue;
}
</style>
