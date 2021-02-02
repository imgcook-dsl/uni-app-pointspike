<template>
  <div class="box">
    <div @click="handleClick_1" v-for="(item, index) in loopData" :key="index">
      <div class="bd">
        <img
          class="layer"
          src="https://img.alicdn.com/tfs/TB1DDx_rQL0gK0jSZFxXXXWHVXa-684-684.png"
        />
        <img
          class="bg"
          src="https://img.alicdn.com/tfs/TB10TB_rQL0gK0jSZFxXXXWHVXa-684-684.png"
        />
        <div class="wrap">
          <img
            class="riverdinwei"
            src="https://img.alicdn.com/tfs/TB1UoB9rQL0gK0jSZFAXXcA9pXa-28-36.png"
          />
          <span class="distance">距离500m</span>
        </div>
      </div>
      <div class="main">
        <span class="title">{{ item.title }}</span>
      </div>
      <div class="ft">
        <div class="block">
          <img class="xianjin" :src="item.user.userImage" />
          <span class="fashionHome">{{ item.user.userName }}</span>
        </div>
        <div class="group">
          <img
            class="favorite"
            src="https://img.alicdn.com/tfs/TB1pxuarHj1gK0jSZFuXXcrHpXa-46-44.png"
          />
          <span class="num">{{ item.readCount }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { fetch } from 'whatwg-fetch';
export default {
  data() {
    return {
      stateData: 'test',
      loopData: [
        {
          title: '小户型卫浴怎样才能装得高大上？',
          coverImage:
            'https://img.alicdn.com/tfs/TB1Txq6o7T2gK0jSZFkXXcIQFXa-684-684.png',
          readCount: 200,
          user: {
            userImage:
              'https://img.alicdn.com/tfs/TB1DWe6oYj1gK0jSZFOXXc7GpXa-60-60.png',
            userName: '时尚家居'
          },
          url: 'https://www.imgcook.com'
        },
        {
          title: '拥有超多功能的40平米简约小公寓了解一下',
          coverImage:
            'https://img.alicdn.com/tfs/TB1XRQTo7P2gK0jSZPxXXacQpXa-684-648.png',
          readCount: 500,
          user: {
            userImage:
              'https://img.alicdn.com/tfs/TB1DWe6oYj1gK0jSZFOXXc7GpXa-60-60.png',
            userName: '花花设计工作'
          },
          url: 'https://www.imgcook.com/docs'
        }
      ],
      constants: {}
    };
  },
  methods: {
    isReadCountShow(readCount) {
      return readCount > 300;
    },
    fetch_example() {
      fetch('https://jsonplaceholder.typicode.com/todos/1', {
        method: 'GET',
        body: {}
      })
        .then(response => response.json())
        .then((data, error) => {
          console.log(dataHandler);
          return data;
        })
        .catch(e => {
          console.log('error', e);
        });
    },
    dataHandler(dataMap) {
      console.log('dataHandler 11');
      return dataMap;
    },
    handleClick_1(e) {
      window.open(this.item.url);
    }
  },
  created() {
    console.log('constructor');
    this.fetch_example();
    this.dataHandler();
  },
  beforeUpdate() {
    console.log('getDerivedStateFromProps');
  }
};
</script>
<style scoped>
.box {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: flex-start;
  height: 534rpx;
}

.bd {
  display: flex;
  position: relative;
  align-items: flex-start;
  flex-direction: row;
  opacity: 1;
  width: 342rpx;
  height: 342rpx;
}

.layer {
  position: absolute;
  top: 0rpx;
  left: 0rpx;
  width: 342rpx;
  height: 342rpx;
  overflow: hidden;
}

.bg {
  position: absolute;
  top: 0rpx;
  left: 0rpx;
  opacity: 1;
  width: 342rpx;
  height: 342rpx;
}

.wrap {
  box-sizing: border-box;
  display: flex;
  position: absolute;
  top: 18rpx;
  left: 18rpx;
  align-items: center;
  flex-direction: row;
  border-radius: 15rpx;
  background-color: rgba(0, 0, 0, 0.4);
  padding-right: 9rpx;
  padding-left: 10rpx;
  height: 30rpx;
}

.riverdinwei {
  opacity: 1;
  width: 14rpx;
  height: 18rpx;
}

.distance {
  margin-left: 4rpx;
  width: 84rpx;
  height: 22rpx;
  line-height: 22rpx;
  white-space: nowrap;
  color: #ffffff;
  font-size: 18rpx;
  font-weight: 400;
}

.main {
  display: flex;
  align-items: flex-start;
  flex-direction: row;
  justify-content: center;
  background-color: #ffffff;
  width: 342rpx;
  height: 114rpx;
}

.title {
  margin-top: 22rpx;
  width: 300rpx;
  height: 88rpx;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 44rpx;
  color: #333333;
  font-size: 30rpx;
  font-weight: 400;
}

.ft {
  box-sizing: border-box;
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: space-between;
  border-bottom-left-radius: 12rpx;
  border-bottom-right-radius: 12rpx;
  background-color: #ffffff;
  padding-right: 17rpx;
  padding-left: 18rpx;
  width: 342rpx;
  height: 78rpx;
  overflow: hidden;
}

.block {
  display: flex;
  align-items: center;
  flex-direction: row;
  height: 30rpx;
}

.xianjin {
  width: 30rpx;
  height: 30rpx;
}

.fashionHome {
  margin-left: 6rpx;
  line-height: 28rpx;
  white-space: nowrap;
  color: #666666;
  font-size: 24rpx;
  font-weight: 300;
}

.group {
  display: flex;
  align-items: center;
  flex-direction: row;
  height: 30rpx;
}

.favorite {
  width: 22rpx;
  height: 22rpx;
}

.num {
  margin-left: 5rpx;
  line-height: 26rpx;
  white-space: nowrap;
  color: #999999;
  font-size: 22rpx;
  font-weight: 400;
}
</style>
