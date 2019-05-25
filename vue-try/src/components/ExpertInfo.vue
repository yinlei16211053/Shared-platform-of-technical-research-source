<template>
    <div>
        <Header></Header>

        <div style="margin-top:35px;width:80%;height:240px;margin:0 auto">
            <el-col :span="7">
                    <div style="margin-top:10px">
                        <img src="../../assets/头像.png" width="70%" style="min-height:70%!important">
                    </div>
            </el-col>
            <el-col :span="11" style="margin-top:17px">
                <div>
                    <h2>用户名</h2>
                </div>
                <div>
                    <h4>所属科研机构</h4><br>
                </div>
                <div>
                    <h4>被引数： 成果数：H指数： G指数：</h4>
                </div>
            </el-col>
            <el-col :span="6" style="margin-top:30px" v-if="isLogined">
                <div>
                    <el-button @click="guanzhu" style="display:block;margin:0 auto" class="btn btn-success">收藏</el-button><br>
                    <el-button @click="jubao" style="display:block;margin:0 auto" class="btn btn-success">举报</el-button><br>
                    <el-button @click="zhanneixin" style="display:block;margin:0 auto" class="btn btn-success">站内信</el-button>
                </div>
            </el-col>
        </div>


        <div style="margin-top:50px;width:75%;margin:0 auto">
            <el-tabs type="border-card" >
                <el-tab-pane label="基本信息">
                    <div style="width:90%;margin:0 auto">
                        <h4>性别：</h4>
                        <h4>邮箱：</h4>
                        <h4>领域：</h4>
                        <h4>收藏数：</h4>
                        <h4>粉丝数：</h4>
                    </div>
                </el-tab-pane>
                <el-tab-pane label="科技成果">
                    <div style="width:90%;margin:0 auto">
                        <el-tabs :tab-position="left" >
                            <el-tab-pane label="论文">
                                <div v-if="statusIsExpert"> 
                                    <el-button @click="uploadpaper" type="primary" style="floating:right;margin:0 auto" class="btn btn-success">上传论文</el-button>
                                </div>
                                <br>
                                <div>
                                    <paper></paper><br>
                                    <paper></paper>
                                </div>
                                <div>
                                    <div class="block">
                                    <el-pagination
                                        layout="prev, pager, next"
                                        :total="40">
                                    </el-pagination>
                                    </div>
                                </div>
                            </el-tab-pane>
                            <el-tab-pane label="专利">
                                <div v-if="statusIsExpert">
                                    <el-button @click="uploadpatent" type="primary" style="floating:right" class="btn btn-success">上传专利</el-button>
                                </div>
                                <br>
                                <div>
                                    <patent></patent>
                                </div>
                                <div>
                                    <div class="block">
                                    <el-pagination
                                        layout="prev, pager, next"
                                        :total="40">
                                    </el-pagination>
                                    </div>
                                </div>
                            </el-tab-pane>
                        </el-tabs>
                    </div>
                </el-tab-pane>

            </el-tabs>

        </div>

       


    </div>
</template>

<script>
import Header from './Header.vue'
import paper from './paper.vue'
import patent from './patent.vue'
import Tailer from '../Tailer.vue'

export default {
    name:'ExpertInfo',
    components:{Header,paper,patent,Tailer},
    data() {
      return {
        username:"",
        institution:"",
        beiyinshu:"",
        chengguoshu:"",
        Hzhishu:"",
        Gzhishu:"",
        guanzhushu:"",
        fensishu:"",
        gender:"",
        email:"",
        area:"",


        isLogined:false,
        statusIsExpert:true
      }
    },
    methods: {
        
        //todo
      guanzhu() {
          alert("guanzhu");
          //this.fensishu=this.fensishu+1;
      },
      jubao() {
        alert("jubao");
      },
      zhanneixin() {
        alert("send message");
      },
      uploadpaper() {
          alert("uploadpaper");
      },
      uploadpatent() {
          alert("uploadpatent");
      }
      
    }

}

</script>

<style scoped>


</style>
