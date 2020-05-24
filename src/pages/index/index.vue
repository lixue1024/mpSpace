<template>
  <div class="home">
    <van-tabs sticky>
      <van-tab title="心情便签">
        <div class="addNote">
          <span class="addIcon" @click="openPopup">
            <van-icon name="add"/>
          </span>
        </div>
        <div class="addContent" v-for="item in moodNote" :key="item.id">
          <div class="headPortrait">
            <van-image
              width="80rpx"
              height="80rpx"
              :src="item.headPortrait"></van-image>
          </div>
          <div class="releaseContent">
            <span class="releaseContentName">{{item.name}}</span>
            <div class="releaseContentTime">{{item.time}}</div>
            <div class="releaseOneContent">{{item.content}}</div>
          </div>

        </div>
        <!-- 遮罩层 -->
        <van-popup
          :show="show"
          position="right"
          custom-style="width: 30%; height: 100%;"
          @close="onClosePopup"
        >
        <div class="editNote">
          <van-icon name="edit" class="editIcon" />
          <span @click="handleEditNote">写心情</span>
        </div>
        </van-popup>
      </van-tab>
      <van-tab title="时间线">2</van-tab>
    </van-tabs>

  </div>
</template>

<script>
export default {
  data() {
    return {
      moodNote: [
        {
          id: '1',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 20：45',
          content: '今天心情不错~~~~~~~~~'
        },
        {
          id: '2',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 18：45',
          content: '今天心情不错~~~~~~~~~'
        },
        {
          id: '3',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 20：45',
          content: '今天心情不错~~~~~~~~~'
        },
        {
          id: '4',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 20：45',
          content: '今天心情不错~~~~~~~~~'
        },
        {
          id: '5',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 20：45',
          content: '今天心情不错~~~~~~~~~'
        },
        {
          id: '6',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 20：45',
          content: '今天心情不错~~~~~~~~~'
        },
        {
          id: '7',
          name: '草莓酸布丁',
          headPortrait: '/static/images/mp01.jpg',
          time: '昨天 20：45',
          content: '今天心情不错~~~~~~~~~'
        }
      ],
      show: false
    }
  },
  methods: {
    openPopup() {
      this.show = true
      console.log(this.show)
    },
    onClosePopup() {
      this.show = false
    },
    handleEditNote() {
      const url="../editNote/main"
      mpvue.navigateTo({ url })
      this.show = false
    }
  },
  onPullDownRefresh() {
    console.log('下拉刷新了')
  },
  onShow() {
    const content = this.$root.$mp.query.content
    const len = this.moodNote.length + 1
    this.moodNote.push({
      id: String(len),
      name: '草莓酸布丁',
      headPortrait: '/static/images/mp01.jpg',
      time: '刚刚',
      content: content
    })
  }
}
</script>

<style scoped>
.addNote {
  height: 40rpx;
  padding: 5px 10px 5px 5px;
  /* border: 1px solid #000; */
  display: flex;
  flex: 1;
  justify-content: flex-end;
}
.addIcon {
  display: inline-block;
  width: 20px;
  height: 20px;
  font-size: 20px;
}
.addContent {
  display: flex;
  flex: 2;
  /* border: 1px solid #000; */
  padding: 5px 5px 20px 5px;
  border-top: 2px solid #eee;
  border-bottom: 5px solid #eee;
}
.headPortrait {
  width: 80rpx;
  height: 80rpx;
  /* border: 1px solid #000; */
}
.releaseContent {
  padding-left: 5px;
  width: 620rpx;
  /* border: 1px solid #000; */
}
.releaseContentName {
  font-weight: 700;
  color: #a64b00;
}
.releaseOneContent {
  padding-top: 5px;
}
.releaseContentTime {
  font-size: 10px;
  color: rgb(145, 141, 141); 
}
.editNote {
  height: 60rpx;
  padding: 5px;
  /* background-color: #fcd9dd; */
  border-bottom: 1px solid #ccc;
  line-height: 60rpx;
  vertical-align: text-bottom;
}
.editIcon {
  font-weight: 700;
}
</style>
