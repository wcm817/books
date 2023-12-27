<template>
  <div class="home">
    <div class="opt">
      <button>显示价格</button>
      <button>添加产品</button>
      <button>导出</button>
    </div>
    <div class="content">
      <div class="info">
        <span class="time">日期:2023-1-1</span>
        <div class="note">
          (注:产品价格都是市场最低价。<br />
          偶尔厂家会根据库存调整一下价格，以每次最新更新的价格为准)
        </div>
      </div>
      <div class="list">
        <div class="list-header">
          <div class="index">序号</div>
          <div class="pro">产品</div>
          <div class="detail">详情</div>
        </div>
        <div class="list-item">
          <div class="index"></div>
          <div class="pro">
            <div class="select-btn">
              <input type="file" />
            </div>
          </div>
          <div class="detail">
            <div class="name">
              <span class="label"> 名称: </span>
              <span></span>
            </div>
            <div class="price">
              <span class="label">价格:</span>
              <span></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  },
  data () {
    return {
      list: [
        {
          src: '',
          price: ''
        }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
.home {
  width: 100vw;
  height: 100vh;
  max-width: 750px;
  margin: 0 auto;
  font-size: 0.37rem;
}
</style>
