<template>
  <div>
    <el-row>
      <!-- 全国的list -->
      <el-col>
        <el-row :gutter="10">
          <el-col :span="24">
            <span>全国</span>
          </el-col>
          <!-- list -->
          <el-col :span="6"  v-for="(item,index) in gridlistQG"  :key="index">
            <a :href="item.href">
              <el-card shadow="hover" :body-style="{padding: '0px'}"  class="card">
                <div class="grid-content grid-con-1">
                  <div class="grid-cont-right">
                    <div class="grid-num">
                      <a class="grid-link">
                        {{item.name}}
                      </a>
                    </div>
                    <div class="grid-text">{{item.introduce}}</div>
                  </div>
                </div>
              </el-card>
            </a>
          </el-col>
        </el-row>
      </el-col>
      <!-- 四川的list -->
      <el-col>
        <el-row :gutter="10">
          <el-col :span="24">
            <span>四川</span>
          </el-col>
          <!-- list -->
          <el-col :span="4"  v-for="(item,index) in gridlistSC"  :key="index">
            <a :href="item.href">
              <el-card shadow="hover" :body-style="{padding: '0px'}"  class="card">
                <div class="grid-content grid-con-1">
                  <div class="grid-cont-right">
                    <div class="grid-num">
                      <a class="grid-link">
                        {{item.name}}
                      </a>
                    </div>
                    <div class="grid-text">{{item.introduce}}</div>
                  </div>
                </div>
              </el-card>
            </a>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import gridlist from '../../assets/js/gridlist.js';
console.log(gridlist);
  export default {
    data() {
      return {
        gridlistQG: gridlist.QG,
        gridlistSC: gridlist.SC
      }
    }
  }
</script>

<style scoped>
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
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }




.card{
  margin-top: 10px;
}
.card:hover .grid-num{
  color: #3f51b5;
}
.card:hover .grid-link::after{
  width: 100%;
}
.grid-content {
  display: flex;
  padding: 0 10%;
  align-items: center;
  height: 80px;
  cursor: pointer;
}
.grid-cont-right {
  flex: 1;
  text-align: left;
  font-size: 12px;
  color: #999;
}

.grid-num {
  font-size: 16px;
  font-weight: bold;
  transition: all 1s;
  color: #999;
}
.grid-link{
  position: relative;
}
.grid-link::after{
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: -5px;
  background: #3f51b5;
  height: 3px;
  width: 0;
  -webkit-transition: all .3s;
  transition: all .3s;
}
.grid-text{
  margin-top:5px; 
  max-height: 32px;
overflow:hidden; 

text-overflow:ellipsis;

display:-webkit-box; 

-webkit-box-orient:vertical;

-webkit-line-clamp:2; 
}



</style>
