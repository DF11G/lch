<template>
  <div id="app">
    <el-container>
      <el-header style="text-align: center; font-size: 12px">
      <span>声音可视化</span>
      </el-header>
      <el-main>
        <el-row :gutter="20">
          <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
          <el-col :span="8">
            <div id="container">
              <el-input id="showText" v-model="nowEmotion" placeholder="情绪即将展现！" style="text-align: center;"></el-input>
            </div>
          </el-col>
          <el-col :span="8"><el-button type="primary" @click="showEmotion">Show</el-button></el-col>
        </el-row>
      </el-main>
    </el-container>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return{
      emotion:['Happy', 'Sad', 'Mad'],
      nowEmotion: '',
      index: 0
    }
  },
  components: {
    
  },
  methods: {
    showEmotion() {
      
      setInterval(() => {
        this.nowEmotion=this.emotion[this.index]
        if(this.index>=this.emotion.length){
          this.index = 0
        }else{
          this.index++
        }
      }, 1000)
    }
  }
}
</script>

<style>
.el-header {
  background-color: #B3C0D1;
  color: #333;
  line-height: 60px;
}
.container{
  margin: auto;
  width: 100px; 
}
.el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #ffffff;
  }
  .bg-purple {
    background: #ffffff;
  }
  .bg-purple-light {
    background: #ffffff;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #ffffff;
  }
</style>
