<template>
  <div class="home">
    <div class="opt">
      <button>显示价格</button>
      <button>添加产品</button>
      <button class="export">导出</button>
    </div>
    <div class="content">
      <div>
        <span class="time">日期:2023-1-1</span>
        <div class="note">
          (注: 偶尔厂家会根据库存调整一下价格，以每次最新更新的价格为准)
        </div>
      </div>
      <div class="list">
        <div class="list-header">
          <div class="index">序号</div>
          <div class="pro">产品</div>
          <div class="detail">详情</div>
        </div>
        <div class="list-item" v-for="(item, i) in list" :key="i">
          <div class="index">{{ i + 1 }}</div>
          <div class="pro">
            <img v-if="item.src" src="" alt="" />
            <div v-else class="select-btn">
              <input type="file" />
              选择图片
            </div>
          </div>
          <div class="detail">
            <div class="name">
              <textarea rows="3"></textarea>
            </div>
            <div class="price">
              <span class="label">价格:</span>
              <span style="color: #f13a2d">￥</span>
              <input type="text" />
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
          name: '',
          price: ''
        }
      ]
    }
  },
  mounted () {
    this
  }
}
</script>
<style lang="scss" scoped>
.home {
  max-width: 750px;
  margin: 0 auto;
  font-size: 0.37rem;
  .opt {
    width: 100%;
    padding: 0.53rem 0.27rem;
    box-sizing: border-box;
    button {
      border: none;
      width: 2.13rem;
      height: 0.75rem;
      background-color: #0094ff;
      border-radius: 0.11rem;
      color: #fff;
      margin-right: 0.27rem;
      &.export {
        float: right;
        margin-right: 0;
      }
    }
  }
  .content {
    padding: 0 0.27rem;
    color: #333;
    box-sizing: border-box;
    .time {
      background-image: -webkit-linear-gradient(
        bottom,
        rgb(108, 210, 250),
        #104cce,
        rgb(2, 9, 48)
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .note {
      color: #f13a2d;
    }
    .list {
      margin-top: 0.43rem;
      .index {
        width: 1.33rem;
      }
      .pro {
        flex: 2;
        flex-shrink: 0;
      }
      .detail {
        flex: 1;
      }
      .list-header {
        display: flex;
        font-weight: 600;
      }
      .list-item {
        display: flex;
        height: 5.33rem;
        padding: 0.21rem 0;
        border-bottom: 1px solid #ccc;
        box-sizing: border-box;
        &:last-child {
          border-bottom: none;
        }
        > div {
          display: flex;
          align-items: center;
          .select-btn {
            position: relative;
            width: 2.13rem;
            height: 0.75rem;
            background-color: #848d96;
            border-radius: 0.11rem;
            color: #fff;
            text-align: center;
            line-height: 0.75rem;
            input {
              position: absolute;
              top: 0;
              left: 0;
              width: 100%;
              height: 100%;
              opacity: 0;
            }
          }
        }
        .detail {
          flex-direction: column;
          justify-content: center;
          > div {
            display: flex;
            justify-content: space-between;
            input,
            textarea {
              width: calc(100% - 50px);
              border: none;
              outline: none;
            }
            textarea {
              width: 100%;
            }
            input {
              color: #f13a2d;
            }
          }
        }
      }
    }
  }
}
</style>
