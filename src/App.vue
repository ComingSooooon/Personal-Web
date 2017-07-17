<template>
  <div id="app">
    <div class="top" v-bind:class="{ active: isActive }">
      <div class="top-inner">
        {{ top }}
        <a href="mailto:zh316694584@gmail.com" class="contact-btn">CONTACT</a>
      </div>
    </div>
    <div class="content">
      <el-collapse v-model="activeNames">
        <div class="blank-content">
          <i class="iconfont icon-jineng-copy"></i>技能</div>
        <el-collapse-item name="1">
          <template slot="title">
            Skills
          </template>
          <div class="skill-box" ref="skillBox"></div>
          <div class="skill-percent" ref="skillPercent"></div>
        </el-collapse-item>
      </el-collapse>

      <el-collapse class="margin-top-mid" v-model="activeNames3">
        <div class="blank-content">
          <i class="iconfont icon-zhiye"></i>职业规划</div>
        <el-collapse-item title="Career planning" name="1">
          <div class="process-item fl">
            <el-progress type="circle" :percentage="35" :width="110"></el-progress>
            <div>Webpack</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="25" :width="110"></el-progress>
            <div>node.js</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="15" :width="110"></el-progress>
            <div>UI</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="20" :width="110"></el-progress>
            <div>PS</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="60" :width="110"></el-progress>
            <div>Sketch</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="87" :width="110"></el-progress>
            <div>BootStrap</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="70" :width="110"></el-progress>
            <div>VUE</div>
          </div>
          <div class="process-item fl">
            <el-progress type="circle" :percentage="100" :width="110" status="success"></el-progress>
            <div>iconfont/fontAwesome</div>
          </div>
        </el-collapse-item>
      </el-collapse>
  
      <el-collapse class="margin-top-mid" v-model="activeNames1">
        <div class="blank-content">
          <i class="iconfont icon-gongzuo"></i>工作经验</div>
        <el-collapse-item title="Work experience" name="1">
          <template slot="title">
            Work experience
          </template>
          <div>
            <el-steps :space="100" direction="vertical" :active="1">
              <el-step title="南京主播之家网络科技有限公司 ( 2016年10月1日～目前 )" description=""></el-step>
              <el-step title="南京三水物联网有限公司 ( 2015年6月1日～2016年10月1日)" description=""></el-step>
            </el-steps>
          </div>
        </el-collapse-item>
      </el-collapse>
  
      <el-collapse class="margin-top-mid" v-model="activeNames2">
        <div class="blank-content">
          <i class="iconfont icon-fuzhi"></i>简历浏览</div>
        <el-collapse-item title="My resume" name="1">
          <div>My resume:
            <a href="../static/file/resume-pdf.pdf" target="blank">PDF版本</a>
            <a href="../static/file/resume-html.html" target="blank">HTML版本</a>
          </div>
        </el-collapse-item>
      </el-collapse>
  
      
  
      <el-collapse class="margin-top-mid" v-model="activeNames4">
        <div class="blank-content">
          <i class="iconfont icon-lianxi"></i>联系方式</div>
        <el-collapse-item title="Connect me" name="1">
          <div>cellphone: 13965872031</div>
          <div>QQ: 316694584</div>
          <div>Email:
            <a href="mailto:zh316694584@gmail.com">zh316694584@gmail.com</a>
          </div>
        </el-collapse-item>
      </el-collapse>
  
      <el-collapse class="margin-top-mid" v-model="activeNames5">
        <div class="blank-content">
          <i class="iconfont icon-chargingpile"></i>最近阅读</div>
        <el-collapse-item title="Recent read" name="1">
          <div>
            <div class="book-item" v-for="item in books">
              <img :src="item.cover" alt="" class="book-cover">
              <div class="book-name">{{ item.name }}</div>
            </div>
          </div>
        </el-collapse-item>
      </el-collapse>
  
      <el-collapse class="margin-top-mid" v-model="activeNames6">
        <div class="blank-content">
          <i class="iconfont icon-yule"></i>其他</div>
        <el-collapse-item title="Others" name="1">
          <div>战网: zh316694584@sina.com</div>
          <div>网易云歌单:
            <a href="http://music.163.com/#/playlist?id=170457076" target="blank">click here!</a>
          </div>
          <div>一日猫:
            <a href="https://yirimao.com/" target="blank">有猫 就有一万种美好</a>
          </div>
        </el-collapse-item>
      </el-collapse>
  
      <div>
      </div>
    </div>
  </div>
</template>

<script>
import Echarts from 'echarts'
export default {
  data () {
    return {
      top: '张行 - FRONT-END',
      isActive: false,
      bg: '../../../static/file/bg1.jpg',
      activeName2: 'first',
      msg: 'Welcome!',
      tips: 'It will cost you 5~10 minnutes to browse the content',
      activeIndex: '1',
      activeNames: ['1'],
      activeNames1: ['1'],
      activeNames2: ['1'],
      activeNames3: ['1'],
      activeNames4: ['1'],
      activeNames5: ['1'],
      activeNames6: ['1'],
      books: [
        { cover: '../static/images/01.jpg', name: '卓有成效的管理者' },
        { cover: '../static/images/02.jpg', name: '怪诞行为学' },
        { cover: '../static/images/03.jpg', name: '万历十五年' },
        { cover: '../static/images/04.jpg', name: '自私的基因' },
        { cover: '../static/images/05.jpg', name: '将心注入' },
        { cover: '../static/images/06.jpg', name: '许三观卖血记' },
        { cover: '../static/images/07.jpg', name: '秘密' },
        { cover: '../static/images/08.jpg', name: '海底捞你学不会' },
        { cover: '../static/images/09.jpg', name: '悟空传' }
      ]
    }
  },
  methods: {
    startHacking() {
      this.$notify({
        title: 'It Works',
        message: 'We have laid the groundwork for you. Now it\'s your time to build something epic!',
        duration: 6000
      })
    },
    open () {
      const h = this.$createElement;
      this.$notify({
        title: 'Welcome!',
        message: h('p', { style: 'color: #1D8CE0' }, 'It will cost you 5~10 minnutes to browse the content')
      });
    }
  },
  mounted () {
    window.onscroll = function () {
      let h1 = document.documentElement.scrollTop || document.body.scrollTop
      let top = document.getElementsByClassName('top')
      if (h1 >= 110) {
        isActive: true
      } else {
        isActive: false
      }
    }
    let mySkillBox = Echarts.init(this.$refs.skillBox)
    let skillBox = {
      title: {
        text: 'Skill Radar'
      },
      tooltip: {},
      legend: {
        data: ['Skills'],
        left: '10%',
        bottom: '15%'
      },
      radar: {
        indicator: [
          { name: 'HTML/HTML5', max: 100 },
          { name: 'JavaScript', max: 100 },
          { name: 'jQuery', max: 100 },
          { name: 'CSS/CSS3', max: 100 },
          { name: 'JSON', max: 100 },
        ]
      },
      series: [{
        type: 'radar',
        data: [
          {
            value: [93, 80, 89, 98, 80],
            name: 'Skills'
          }
        ]
      }]
    }
    mySkillBox.setOption(skillBox)
    let mySkillPercent = Echarts.init(this.$refs.skillPercent)
    let skillPercent = {
      backgroundColor: 'rgba(49, 171, 233, .1)',
      title: {
        text: 'Skill Percentage',
        left: 'center',
        top: 20,
        textStyle: {
          color: '#333'
        }
      },
      tooltip: {
        trigger: 'item',
        formatter: "{a} <br/>{b} : {c} ({d}%)"
      },
      visualMap: {
        show: false,
        min: 80,
        max: 600,
        inRange: {
          colorLightness: [0, 1]
        }
      },
      series: [
        {
          name: 'Skill percentage',
          type: 'pie',
          radius: '55%',
          center: ['50%', '50%'],
          data: [
            { value: 335, name: 'HTML/HTML5' },
            { value: 310, name: 'JavaScript/jQuery' },
            { value: 274, name: 'CSS/CSS3' },
            { value: 235, name: 'JSON' },
            { value: 200, name: 'PS/Sketch' }
          ].sort(function (a, b) { return a.value - b.value; }),
          roseType: 'radius',
          label: {
            normal: {
              textStyle: {
                color: 'rgba(25, 25, 25, 0.9)'
              }
            }
          },
          labelLine: {
            normal: {
              lineStyle: {
                color: 'rgba(208, 26, 26, 0.8)'
              },
              smooth: 0.2,
              length: 10,
              length2: 20
            }
          },
          itemStyle: {
            normal: {
              color: '#c23531',
              shadowBlur: 200,
              shadowColor: 'rgba(0, 0, 0, 0.5)'
            }
          },
          animationType: 'scale',
          animationEasing: 'elasticOut',
          animationDelay: function (idx) {
            return Math.random() * 200;
          }
        }
      ]
    }
    mySkillPercent.setOption(skillPercent)
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: Helvetica, sans-serif;
  background: url('../static/file/bg1.jpg') scroll center;
  width: 100%;
  height: 1050px;
  overflow-y: auto;
}

.contact-btn{
  float: right;
  margin-top: 28px;
  font-size: 20px;
  font-weight: 400;
  padding: 8px 20px;
  line-height: 24px;
  color:#fff;
  text-decoration: none;
  border: 2px solid #fff;
  border-radius: 50px;
}

.contact-btn:hover{
  background-color: #fff;
  color: rgba(59, 48, 75, 0.8);
}

.content {
  width: 1200px;
  margin: 130px auto 100px;
}

.skill-box {
  width: 570px;
  height: 400px;
  float: left;
  margin-bottom: 12px;
}

.skill-percent {
  width: 570px;
  height: 400px;
  float: left;
}

.progress-are {
  margin-left: 820px;
}

.process-item {
  width: 126px;
  text-align: center;
  margin: 40px 10px;
}

.fl {
  float: left;
}

.book-cover {
  width: 80px;
  height: 100px;
}

.book-item {
  width: 90px;
  float: left;
  margin-right: 20px;
  text-align: center;
  height: 160px;
}

.top {
  height: 100px;
  width: 100%;
  color: #fff;
  line-height: 100px;
  font-size: 30px;
  font-weight: 700;
  position: fixed;
  top: 0;
  z-index: 9999;
  background-color: rgba(59, 48, 75, 0.8);
}

.active {
  background-color: rgba(59, 48, 75, 1);
}

.top-inner {
  width: 1200px;
  margin: 0 auto;
}

.margin-top-mid {
  margin-top: 20px;
}

.blank-content {
  width: 100%;
  height: 36px;
  color: #fff;
  font-weight: 500;
  font-size: 20px;
  line-height: 36px;
  text-indent: 10px;
}

.blank-content i {
  margin-right: 8px;
}
</style>
