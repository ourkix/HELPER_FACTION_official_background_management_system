<template>
  <div style="margin-top: 40px; margin-bottom: 40px">
    <a-descriptions class="infogroupstyle" title="创建用户：刘先生" layout="vertical">
      <a-descriptions-item label="地址">上海市崇明街128号5栋801房</a-descriptions-item>
      <a-descriptions-item label="手机号码">13631427198</a-descriptions-item>
      <div style="width: 100%;">
        <span style="color: #79E1B3; font-size: 30px; float: right; margin: -12px 0 0 10px;">已完成</span>
        <div
          style="width: 20px; height: 20px; background: #79E1B3; border-radius: 50px; float: right"
        ></div>
      </div>
      <div></div>
      <br />
      <br />
      <a-descriptions-item label="接单师傅">张师傅</a-descriptions-item>
      <a-descriptions-item label="师傅手机号码">17983092283</a-descriptions-item>
      <div style="width: 100%">
        <a-button type="danger" ghost shape="round" size="large" style="float: right">删除订单</a-button>
      </div>
      <div></div>
      <br />
      <br />
      <a-descriptions-item label="日期">
        创建日期：
        <br />2019 - 03 - 14 07 : 30
        <br />
        <br />预约时间：
        <br />2019 - 03 - 14 08 : 00 -
        <br />2019 - 03 - 15 20
        : 00
      </a-descriptions-item>
      <a-descriptions-item label="订单号">REX28917734BNGE201</a-descriptions-item>
    </a-descriptions>
    <a-carousel
      :after-change="onChange"
      style="width: 300px; float: right; margin-top: -230px; margin-right: 50px"
    >
      <div>
        <h3>1</h3>
      </div>
      <div>
        <h3>2</h3>
      </div>
      <div>
        <h3>3</h3>
      </div>
      <div>
        <h3>4</h3>
      </div>
    </a-carousel>
    <div style="padding: 30px;">
      <a-table :columns="columns" :data-source="data" :style="{ height: '100%', overflow: 'auto' }">
        <a slot="ordertype" slot-scope="text">{{ text }}</a>
      </a-table>
    </div>
    <div style="width: 100%;"></div>
  </div>
</template>

<script>
const columns = [
  {
    title: "订单种类",
    dataIndex: "ordertype",
    key: "ordertype",
    // scopedSlots: { customRender: "ordertpye" },
  },
  {
    title: "订单内容",
    dataIndex: "ordercontent",
    key: "ordercontent",
    width: 300,
    ellipsis: true,
  },
  {
    title: "订单金额",
    dataIndex: "price",
    key: "price",
  },
  {
    title: "订单评分",
    dataIndex: "orderrate",
    key: "orderrate",
  },
];
const data = [
  {
    key: "1",
    ordertype: "居家维修",
    ordercontent: "将发霉的墙砸掉重新砌起来",
    price: "￥283",
    orderrate: 3.5,
  },
];
export default {
  data() {
    return {
      data,
			columns,
			orderrate: 2,
    };
  },
  components: {},
  methods: {
    onChange(a, b, c) {
      console.log(a, b, c);
    },
  },
};
</script>

<style scoped>
.infogroupstyle {
  padding: 50px;
}

.ant-carousel >>> .slick-slide {
  text-align: center;
  height: 160px;
  line-height: 160px;
  background: #2866b1;
  overflow: hidden;
  border-radius: 10px;
}

.ant-carousel >>> .slick-slide h3 {
  color: #fff;
}
</style>
