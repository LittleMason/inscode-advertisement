<script setup>
import { ref } from 'vue';
const navigates = ['活动介绍','活动安排','奖项设置','报名流程'];
const navigateActive = ref(0);
const handleNavigate = (index) => {
  navigateActive.value = index
}
</script>

<template>
  <div class="advertise-container">
    <div class="content">
      <div class="border-common navigate sm:hidden xl:block">
        <div class="navigate-content">
          <div :class="{'active':navigateActive===index}" v-for="(item,index) in navigates" :key="index" @click="handleNavigate(index)">
            <a href="#">{{item}}</a>
          </div>
        </div>
      </div>
      <div class="border-common">
        <div class="introduce">
          <div class="introduce-title">
            活动<br/>介绍
          </div>
          <div class="introduce-content">
            <div class="introduce-content-paragraph">
              InsCode是一个集成了在线IDE、在线AI编程、在线大模型训练以及SD
              模型使用的综合代码开发平台。不论你是初级软件工程师，还是AI大模型爱好者，InsCode都能帮助你快速编写代码，运行项目。甚至在这里你还可以一键购买算力，训练大模型，开发自己的AI应用程序。
            </div>
            <div class="introduce-content-paragraph">
              现我们真诚地邀请您来参加InsCode试用评测活动，本次试用测评活动主要分为四期，每一期都有丰厚的奖品等你来拿～
            </div>
            <div class="mb-5 introduce-content-paragraph">
              同时，四期全部参与的小伙伴，还会自动参与最终奖项的评选，如果您四期全部参与，且被评选后进入最终榜单，还会有神秘大奖哦～
            </div>
            <div class="mb-2 introduce-content-paragraph blue f-18 indent-0">
              活动参与对象
            </div>
            <div class="introduce-content-paragraph indent-0">
              本次活动面向全社会开放，<span class="blue"
                >个人、高等院校、科研单位、企业等人员</span
              >均可报名参加。
            </div>
            <div class="introduce-content-paragraph indent-0">
              说明：如有活动主办方和技术支持单位（如 CSDN
              员工）参加活动，则自动放弃获奖资格。
            </div>
          </div>
        </div>
      </div>
      <div class="border-common">
        <div class="arrange">
          <div class="arrange-title">活动安排</div>
          <div class="arrange-content">
            <div class="arrange-content-first">
              <div class="arrange-content-first-title">
                <div class="arrange-content-first-title-item">第一期</div>
                <div class="arrange-content-first-title-item">在线试用stable diffusion 模型生成优质人物好图</div>
                <div class="arrange-content-first-title-item">2023-06-28 开始</div>
                <div class="arrange-content-first-title-item">周期14天</div>
              </div>
              <div class="grid gap-4 arrange-content-first-content xl:grid-cols-6 md:grid-cols-3 sm:grid-cols-2">
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    活动上线
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-06-25
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    活动宣传
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-06-25 <br />
                    至<br />
                    2023-06-27
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    活动开始与结束
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-06-28 <br />
                    至<br />
                    2023-07-11
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">作品评选</div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-12 <br />
                    至<br />
                    2023-07-14
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">评选结果公布</div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-17
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">奖励发放</div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-18 <br />
                    至<br />
                    2023-07-25
                  </div>
                </div>
              </div>
            </div>
            <div class="arrange-content-twice">
              第二期
            </div>
            <div class="arrange-content-third">
              第三期
            </div>
            <div class="arrange-content-fourth">
              第四期
            </div>
          </div>
        </div>
      </div>
      <div class="border-common">
        <div class="setting">
          <div class="setting-title">
            奖项设置
          </div>
          <div class="setting-content">
            <div class="grid gap-5 mb-4 xl:grid-cols-4 md:grid-cols-4 sm:grid-cols-2">
                <div class="setting-content-item">
                  <img src="./assets/1.png" alt="" />
                </div>
                <div class="setting-content-item">
                  <img src="./assets/2.png" alt="" />
                </div>
                <div class="setting-content-item">
                  <img src="./assets/3.png" alt="" />
                </div>
                <div class="setting-content-item">
                  <img src="./assets/4.png" alt="" />
                </div>
            </div>
            <div>
              注： 算力资源发放会在评奖后立即开启，不可暂停或累计，获奖的小伙伴请及时到算力页 xx 畅玩大模型哦。InsCode小能手勋章，每参加一期活动，勋章自动升级。四期全部参加，即可获取InsCode小能手(限时终极)勋章。
            </div>
          </div>
        </div>
      </div>
      <div class="border-common">
        <div class="flow">
          <div class="flow-title">报名及参赛流程</div>
          <div class="flow-content">
              <div class="mb-3 flow-content-title">
                1、到InsCode的<span class="blue">（xxx页）选择SD模型在线试玩，生成满意的人物图片。如果不会使用模型的，可参考xxxx文章查看试玩教程。</span>
              </div>
              <div class="mb-3 flow-content-title">
                2、在xxx（devpress页）发布参加活动贴，并注明 所用SD模型版本，prompt 和其他相关配置。具体格式见xxxx。
              </div>
              <div class="mb-3 flow-content-title">
                3、提交帖子后，即可等待官方进行评选。 xxx-xxx为作品评选时间，xxx公布评选结果。
              </div>
              <div class="mb-6">
                注：如果您在使用的过程中，有任何问题或建议，请联系InsCode小助手 或投稿至 <a href=" https://devpress.csdn.net/tags/648c3ea96bf8dd0412f50c13"> https://devpress.csdn.net/tags/648c3ea96bf8dd0412f50c13</a>，我们会第一时间为您解答相关问题哦～
              </div>
              <div class="mb-3 flow-content-blue">
                参加活动帖子要求：
              </div>
              <div>
                1、帖子标题最开始须带上“[SD模型 参赛一期]”字样
              </div>
              <div>2、文章内容须有话题标签：#SD模型人物图  #InsCode </div>
              <div class="mb-6">3、必须发布的是真实的InsCode上的SD模型产出的人物图片</div>
              <div class="mb-3 flow-content-blue">
                评选规则：
              </div>
              <div class="mb-6">
                由评选委员会根据博主产出的参赛贴和SD模型生成的图片质量情况给予打分评选
              </div>
              <div class="mb-3 flow-content-blue">
                领奖规则：
              </div>
              <div>1、获奖名单会在该评选结束后在该页面公布。</div>
              <div>2、工作人员将在活动结束后的7个工作日内，通过CSDN私信联系中奖用户，进行发奖，请您注意消息通知。</div>
              <div class="mb-6">3、除参与奖外，获奖人员，领奖时需实名认证，1 个实名认证用户同一期内仅可领取1份奖项哦～ </div>
              <div class="mb-3 flow-content-blue">
                其它规则：
              </div>
              <div class="mb-3 blue">
                若出现以下情况，将视为违规，活动组委会有权取消用户参与资格及获得的奖项。
              </div>
              <div>1、活动报名信息虚假，或不符合活动报名要求的参与者。</div>
              <div>2、活动参与文章涉嫌抄袭，侵犯他人知识产权等行为。</div>
              <div>3、活动参与作品或文章发现或被举报认定存在的其他违法、违规行为。法律允许范围内的，最终解释权归InsCode 所有。</div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <div class="mr-6 footer-button">我是按钮</div>
      <div class="footer-button">我是按钮</div>
    </div>
  </div>
</template>

<style scoped lang="less">
@fontSize: 16px; //基本字体大小
@font18:18px; //较大内容字体大小
@font19:19px; //最大内容字体大小
@font20:20px; //小title字体大小
@font22:22px; //中title字体大小
@introduceW:220px; //活动结束宽度
.blue {
  color: #016ffe;
}
.gray {
  color: #999;
}
.title-common {
  background: #77a1f7;
  box-shadow: 0px 6px 10px 0px rgba(120, 162, 247, 0.5);
  border-radius: 26px;
  font-size: 38px;
  font-family: SourceHanSansCN-Bold, SourceHanSansCN;
  font-weight: bold;
  color: #ffffff;
}
.border-common {
  background: #ffffff;
  box-shadow: 0px 2px 20px 0px rgba(55, 165, 202, 0.35);
  border-radius: 44px;
  padding: 10px;
  overflow: visible;
  margin-bottom: 80px;
  position: relative;
  background: linear-gradient(
    180deg,
    rgba(219, 245, 255, 1),
    rgba(181, 231, 254, 1)
  );
  & > div {
    border-radius: 44px;
    background: #ffffff;
    padding: 20px;
  }
}
.title-common{
  background: #77A1F7;
  box-shadow: 0px 6px 10px 0px rgba(120,162,247,0.5);
  border-radius: 26px;
  font-size: 38px;
  font-family: SourceHanSansCN-Bold, SourceHanSansCN;
  font-weight: bold;
  color: #FFFFFF;
  text-align: center;
  display: inline-block;
  padding: 10px 20px;
  position: absolute;
  left: 0;
  top: 0;
  transform: translate(0,-50%);
}
.arrange-common{
  border-radius: 0px 10px 10px 10px;
  text-align: center;
  margin: 0 auto;
  padding: 15px 0;
  font-size: @font18;
}


.advertise-container {
  background-image: url(./assets/banner1.png);
  background-repeat: no-repeat;
  background-size: 100% auto;
  background-color: rgba(195, 233, 255, 1);
  min-height: 100vh;
  position: relative;
  font-family: SourceHanSansCN-Medium, SourceHanSansCN;
  font-size: @fontSize;
  .content {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
    padding-top: 17%;
    position: relative;
    .navigate{
      font-size: @font18;
      font-family: SourceHanSansCN-Medium, SourceHanSansCN;
      font-weight: 500;
      color: #999999;
      text-align: center;
      position: absolute;
      z-index: 99;
      right: 0;
      transform: translate(120%,0);
      border-radius: 22px;
      &-content{
        border-radius: 22px;
        padding: 10px 0;
        &>div{
          border-bottom: 1px solid #ccc;
          padding: 10px;
          &.active{
            .blue;
            font-weight: bold;
          }
          &:last-child{
            border: none;
          }
        }
      }
    }
    .introduce {
      &-title {
        background-color: #77A1F7;
        color: transparent;
        font-size: 60px;
        font-weight: bold;
        -webkit-text-stroke: 1px #fff; /* 设置镂空效果 */
        position: absolute;
        right: 40px;
        top: 0;
        transform: translate(0, -30%);
        border-radius: 44px;
        padding: 20px;
        padding-left: 30px;
        letter-spacing: 10px;
      }
      &-content {
        padding-right: @introduceW + 10px;
        &-paragraph {
          text-indent: @fontSize * 2;
        }
      }
    }
    .arrange{
      padding: 40px 30px;
      &-title{
        .title-common;
      }
      &-content{
        &-first{
          background: #D6E3FD;
          border-radius: 10px;
          &-title{
            background-color: rgba(119, 161, 247,.3);
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            padding: 5px 20px;
            font-size: @font22;
            font-family: SourceHanSansCN-Medium, SourceHanSansCN;
            font-weight: 500;
            color: #000000;
          }
          &-content{
            padding:20px;
            &-item{
              background: #FFFFFF;
              border-radius: 10px;
              text-align: center;
              padding: 10px 0;
              &-title{
                font-size: @font20;
                margin-bottom: 15px;
                .blue;
              }
            }
          }
        }
        &-twice{
          .arrange-common;
          width: 80%;
          background-color: #E3ECFE;
        }
        &-third{
          .arrange-common;
          width: 60%;
          background-color: #F1F5FE;
        }
        &-fourth{
          .arrange-common;
          width: 40%;
          background-color: #F8FAFF;
        }
      }
    }
    .setting{
      padding: 40px 30px;
      &-title{
        .title-common;
      }
      &-content{
        &-item{
          img{
            width: 100%;
            height: 100%;
          }
        }
      }
    }
    .flow{
      padding: 40px 30px;
      &-title{
        .title-common;
      }
      &-content{
        &-title{
          font-size: @font19;
          font-family: SourceHanSansCN-Medium, SourceHanSansCN;
          font-weight: 500;
        }
        &-blue{
          .blue;
          font-size: @font18;
        }
      }
    }
  }
  .footer {
    width: 100%;
    height: 120px;
    background: #ffffff;
    box-shadow: 0px 2px 20px 0px rgba(55, 165, 202, 0.35);
    border-radius: 44px 44px 0px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    &-button{
      background: linear-gradient(180deg, #AFCFFC 0%, #3A7BFF 100%);
      box-shadow: 0px 6px 10px 0px rgba(120,162,247,0.5);
      border-radius: 32px;
      padding: 10px 30px;
      font-family: SourceHanSansCN-Bold, SourceHanSansCN;
      font-weight: bold;
      color: #FFFFFF;
      font-size: 28px;
    }
  }
}
</style>
