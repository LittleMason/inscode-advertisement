<script setup>
import { ref, onMounted } from "vue";

const navigates = [
  {
    text: "活动介绍",
    anchor: "#introduce",
    show:true
  },
  {
    text: "活动时间",
    anchor: "#arrange",
    show:true
  },
  {
    text: "奖项设置",
    anchor: "#setting",
    show:true
  },
  {
    text: "参赛流程",
    anchor: "#flow",
    show:true
  },
  {
    text: "图片展示",
    anchor: "#explain",
    show:false
  },
  {
    text: "获奖公布",
    anchor: "#publishRecords",
    show:false
  },
];
const navigateActive = ref(0);
const navigatePosition = ref(0);
const handleNavigate = (index) => {
  navigateActive.value = index;
};
const productions = [
  {
    name:'爱吃鱼的章鱼',
    production:'https://img1.baidu.com/it/u=3214529205,2622974616&fm=253&fmt=auto&app=138&f=JPEG?w=281&h=500',
    avator:'https://t7.baidu.com/it/u=1951548898,3927145&fm=193&f=GIF'
  },
  {
    name:'爱吃鱼的章鱼',
    production:'https://img.tukuppt.com/photo-big/00/00/56/6153fbf810c544118.jpg',
    avator:'https://t7.baidu.com/it/u=1951548898,3927145&fm=193&f=GIF'
  },
];
const productionVisible = ref(false);
onMounted(() => {
  const initNavigate = () => {
    const content = document.querySelector(".content");
    const rightOffset =
      window.innerWidth - content.getBoundingClientRect().right;
    navigatePosition.value =
      rightOffset -
      document.querySelector(".navigate").getBoundingClientRect().width -
      16;
  };
  initNavigate();
  window.addEventListener("resize", () => {
    initNavigate();
  });
});

//二维码显示隐藏
const QRCodeVisible = ref(false);
const QRCodeMobileVisible = ref(false);
const handleShowMobile = ()=>{
  const currentW = window.innerWidth;
  if(currentW<1200){
    QRCodeMobileVisible.value = true;
  }
}
//示例显示隐藏
const previewVisible = ref(false);
</script>

<template>
  <div class="advertise-container">
    <div class="preview-box" v-show="previewVisible">
      <div class="preview-box-content">
        <div class="preview-box-content-title">
          操作示例
          <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/close@3x.png/large" alt="" @click="previewVisible=false">
        </div>
        <div class="preview-box-content-title-img-box">
          <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/example@3x.png/large" alt="">
        </div>
        <div class="preview-box-content-footer">
          <div class="cursor-pointer preview-box-content-footer-button" @click="previewVisible=false">
            确定
          </div>
        </div>
      </div>
    </div>
    <div class="content" ref="contentRef">
      <div
        class="border-common navigate sm:hidden xl:block"
        :style="{ right: navigatePosition + 'px' }"
      >
        <div class="navigate-content">
          <template v-for="(item, index) in navigates" :key="index">
          <div
            :class="{ active: navigateActive === index }"
            v-if="item.show"
            @click="handleNavigate(index)"
          >
            <a :href="item.anchor">{{ item.text }}</a>
          </div>
        </template>  
        </div>
      </div>
      <div class="navigate-mobile sm:flex xl:hidden">
        <div
          :class="{ active: navigateActive === index }"
          v-for="(item, index) in navigates"
          v-show="item.show"
          :key="index"
          @click="handleNavigate(index)"
        >
          <a :href="item.anchor">{{ item.text }}</a>
        </div>
      </div>
      <div class="border-common" id="introduce">
        <div class="introduce">
          <div class="introduce-title sm:hidden xl:block">
            <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/introduce.png/large" alt="">
          </div>
          <div class="introduce-title-mobile sm:block xl:hidden">活动介绍</div>
          <div class="introduce-content">
            <div class="introduce-content-text-box">
              <div class="introduce-content-paragraph">
                InsCode是一个集成了在线IDE、在线AI编程、在线算力租赁、在线项目部署以及在线SD 模型使用的综合代码开发平台。不论你是初级软件工程师，还是AI大模型爱好者，InsCode都能帮助你快速编写代码，运行项目。甚至在这里你还可以一键购买算力，训练大模型，开发自己的AI应用程序。
              </div>
              <div class="introduce-content-paragraph">
                现我们真诚地邀请您来参加InsCode试用活动，本次试用活动主要分为四期，每一期都有丰厚的奖品等你来拿～
              </div>
              <div class="mb-5 introduce-content-paragraph">
                同时，四期全部参与的小伙伴，还会自动参与最终奖项的评选，如果您四期全部参与，且被评选后进入最终榜单，还会有神秘大奖哦～
              </div>
            </div>
            <div class="introduce-content-img-box">
               <img class="sm:hidden md:block" src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/introduce-banner-pc.png/large" alt="">
               <img class="sm:block md:hidden" src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/introduce-banner-mobile.png/large" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="border-common" id="arrange">
        <div class="arrange">
          <div class="arrange-title">活动时间</div>
          <div class="arrange-content">
            <div class="arrange-content-first">
              <div class="arrange-content-first-title sm:hidden md:flex">
                <div class="arrange-content-first-title-item">第一期</div>
                <div class="arrange-content-first-title-item">
                  在线试用Stable Diffusion 模型生成优质人物好图
                </div>
                <div class="arrange-content-first-title-item">
                  2023-07-03 开始
                </div>
                <div class="arrange-content-first-title-item">周期14天</div>
              </div>
              <div class="arrange-content-first-title sm:block md:hidden" style="font-size: 14px;padding:10px">
                 <div>第一期：在线试用 Stable Diffusion 模型生成优质人物好图</div>
                 <div><span style="margin-right:10px">2023-07-03 开始</span><span>周期25天</span></div>
              </div>
              <div
                class="grid custom-gap arrange-content-first-content xl:grid-cols-5 md:grid-cols-3 sm:grid-cols-2"
              >
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    活动开始日期
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-03
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    活动结束日期
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-16
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    作品评选
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-17 <br />
                    至<br />
                    2023-07-20
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    评选结果公布
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-21
                  </div>
                </div>
                <div class="arrange-content-first-content-item">
                  <div class="arrange-content-first-content-item-title">
                    奖励发放
                  </div>
                  <div class="arrange-content-first-content-item-paragraph">
                    2023-07-22 <br />
                    至<br />
                    2023-07-28
                  </div>
                </div>
              </div>
            </div>
            <div class="arrange-content-twice">第二期</div>
            <div class="arrange-content-third">第三期</div>
            <div class="arrange-content-fourth">第四期</div>
          </div>
        </div>
      </div>
      <div class="border-common" id="setting">
        <div class="setting">
          <div class="setting-title">奖项设置</div>
          <div class="setting-content">
            <div
              class="grid mb-4 custom-gap xl:grid-cols-4 md:grid-cols-4 sm:grid-cols-2"
            >
              <div class="setting-content-item">
                <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/1@3x.png/large" alt="" />
              </div>
              <div class="setting-content-item">
                <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/2@3x.png/large" alt="" />
              </div>
              <div class="setting-content-item">
                <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/3@3x.png/large" alt="" />
              </div>
              <div class="setting-content-item">
                <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/4@3x.png/large" alt="" />
              </div>
            </div>
            <div>
              <div class="annotation-line">注：1. 算力资源发放会在评奖后立即开启，不可暂停或累计，获奖的小伙伴请及时到<a class="blue" href="https://inscode.csdn.net/templates">模板中心</a>畅玩大模型哦</div>
              <div class="annotation-line">2. 每参加一期活动，勋章自动升级，四期全部参加，即可获取InsCode小能手终极勋章</div>
            </div>
          </div>
        </div>
      </div>
      <div class="border-common" id="flow">
        <div class="flow">
          <div class="flow-title">参赛流程</div>
          <div class="flow-content">
            <div class="mb-1 flow-content-step-title">
              第一步：选择SD模型试玩
            </div>
            <div class="mb-6 flow-content-title">
              到InsCode的 <a href="https://inscode.csdn.net/@inscode/Stable-Diffusion">Stable Diffusion模板</a>运行及使用 SD 模型，生成满意的人物图片。如果不会使用模型的，可参考<a href="https://devpress.csdn.net/inscode/6492a77a7846f97eafea48e3.html">《如何使用SD模板生成图片》</a><a href="https://devpress.csdn.net/inscode/649aa855187b2e3b840b46b5.html">《如何给SD安装lora》</a>查看试玩教程 
            </div>
            <div class="mb-1 flow-content-step-title">
              第二步：发布博客即刻参与活动
            </div>
            <div class="mb-6 flow-content-title">
              活动博客参考案例 <a href="https://blog.csdn.net/2301_76740037/article/details/131332427">《可爱的头像【 InsCode Stable Diffusion 美图活动一期】》</a>， 详细要求：
              <ol class="list-decimal list-inside">
                <li>标题：含有关键词“InsCode Stable Diffusion 美图活动一期”，可参考【XXXX-InsCode Stable Diffusion 美图活动一期】(其中 “XXXXX”为自定义标题名称， 如 “二次元少女”，“森领奇幻钢琴家“等等</li>
                <li>正文：必须包含在线运行地址（统一为https://inscode.csdn.net/@inscode/Stable-Diffusion）、模型相关版本和参数配置、图片生成提示词和反向提示词、种子和对应的图片</li>
                <li>最后：提交博客时文章标签需添加“Stable Diffusion”，将生成的图片作为封面图，选择参加的活动 “ Stable Diffusion 美图活动一期” （一定要选择此活动才可进入活动评选哦~）<span class="cursor-pointer blue" @click="previewVisible = true">点击查看示例</span></li>
              </ol>
              备注：发布的必须是InsCode上SD模型产出的人物图片 （最终进入榜单的小伙伴，我们会对生成的图片进行再次核验其生成的真实性 ）
            </div>
            <div class="mb-1 flow-content-step-title">
              第三步：官方评选
            </div>
            <div class="mb-6 flow-content-title">
              提交博客后，即可等待官方进行评选。 2023-07-17至2023-07-20为作品评选时间，2023-07-21在此活动页公布评选结果。<br/>Tips：如果您在使用的过程中，有任何问题或建议，请添加 
              <span class="cursor-pointer qr-box blue"  @mouseover="QRCodeVisible=true" @mouseleave="QRCodeVisible=false" @click="handleShowMobile">
                InsCode小助手 
                <span v-show="QRCodeVisible" class="qr-box-pc">
                  <img class="mb-2" src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/QR_code.png/large" alt="">
                  <div class="flex items-center justify-center blue" style="height: 32px;">
                    <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/robot.png/large" alt="" class="robot-logo">
                    <div>InsCode小助手</div> 
                  </div>
                </span>
              </span>
              <div class="qr-box-mobile" v-show="QRCodeMobileVisible">
                <div class="qr-box-mobile-content">
                  <div class="flex items-center justify-center qr-box-mobile-content-title"><img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/robot.png/large" alt="" class="robot-logo">InsCode小助手</div>
                  <img src="https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/QR_code.png/large" alt="" />
                  <div class="qr-box-mobile-content-button" @click="QRCodeMobileVisible=false">确定</div>
                </div>
              </div>
              或投稿至 <a href="https://devpress.csdn.net/tags/648c3ea96bf8dd0412f50c13">问题反馈</a>，我们会第一时间为您解答相关问题哦～
            </div>
            <div class="mb-3 flow-content-blue">评选规则：</div>
            <div class="mb-3">
              由CSDN根据博主产出的参赛贴和SD模型生成的图片质量情况给予打分评选:
            </div>
            <div class="indent2f">
              1.博文传播影响力 占比40%
            </div>
            <div class="mb-1 indent4f">
              <div>a.站外发布该活动博客 20分（比如 掘金、知乎、V2EX、SegmentFault、OSChina等开发者社区，每在一个社区发布得5分，满分20分）ps. 博主需要把在其他平台发布的帖子提交在参加活动的博客评论中，以方便工作人员进行积分统计</div>
              <div>b.帖子点赞量，1个点赞1分，封顶10分</div>
              <div>c.帖子的评论量，1个评论1分，封顶10分 （除作者本人自己的评论）</div>
            </div>
            <div class="indent2f">
              2.发布博文内容的质量 占比30%
            </div>  
            <div class="mb-1 indent4f">
              <div>a.是否有详细的模型使用介绍 20分</div>
              <div>b.是否有对模型的深度使用 10分（比如 使用了Lora，VAE等能力）</div>
            </div>
            <div class="indent2f">
              3.生成图片的质量和个数 占比30%
            </div>  
            <div class="mb-6 indent4f">
              <div>a.图片的美观程度、新颖性、质感、清晰度等等 20分</div>
              <div>b.生成图片的个数 ，1张图2分， 总分10分封顶</div>
            </div>
            
            <div class="mb-3 flow-content-blue">领奖规则：</div>
            <div>1.获奖名单会在评选结果公布日期，即7月21日在该页面公布。</div>
            <div>
              2.工作人员将在活动结束后的7个工作日内，通过CSDN私信联系中奖用户，进行发奖，请您注意消息通知（私信联系后1周内未回复则取消奖项视为自动放弃）。
            </div>
            <div class="mb-6">
              3.除参与奖外，获奖人员，领奖时需实名认证，1
              个实名认证用户同一期内仅可领取1份奖项哦～
            </div>
            <div class="mb-3 flow-content-blue">其它说明：</div>
            <div>
              本次活动面向全社会开放，个人、高等院校、科研单位、企业等人员均可报名参加。（如有活动主办方和技术支持单位参加活动，则自动放弃获奖资格。）<br/>
              若出现以下情况，将视为违规，CSDN有权取消用户参与资格及获得的奖项，如奖金或相关权益已经发放，CSDN有权要求用户返还奖金并收回相关权益，如给CSDN造成损失的，由用户承担相关责任。
            </div>
            <div>1.活动报名信息虚假，或不符合活动报名要求的参与者。</div>
            <div>2.活动参与文章涉嫌抄袭，侵犯他人知识产权等行为。</div>
            <div>
              3.活动参与作品或文章发现或被举报认定存在的其他违法、违规行为。
            </div>
          </div>
        </div>
      </div>
      <div    class="border-common" id="explain" v-if="productionVisible">
        <div class="explain">
          <div class="explain-title">作品展示</div>
          <div class="explain-content">
            <div
              class="grid mb-4 explain-content-gap xl:grid-cols-5 md:grid-cols-3 sm:grid-cols-2"
            >
              <div class="explain-content-item" v-for="(item,index) in productions" :key="index">
                <div class="explain-content-item-img-box">
                  <img :src="item.production" alt="" />
                </div>
                <div class="explain-content-item-footer">
                  <img :src="item.avator" alt=""> <div>{{ item.name }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <div class="mr-6 footer-button"><a href="https://inscode.csdn.net/@inscode/Stable-Diffusion?utm_source=1782868685">第一步：试用SD模型</a></div>
      <div class="footer-button"><a href="https://activity.csdn.net/creatActivity?id=10496">第二步：发布博客</a></div>
    </div>
  </div>
</template>

<style scoped lang="less">
// @font-face {
//   font-family: "SourceHanSansCN-Normal"; /* 字体名称 */
//   src: url("./assets/font/SourceHanSansCN-Normal.otf") format("opentype"); /* 字体文件路径和格式 */
// }
// @font-face {
//   font-family: "SourceHanSansCN-Bold"; /* 字体名称 */
//   src: url("./assets/font/SourceHanSansCN-Bold.otf") format("opentype"); /* 字体文件路径和格式 */
// }
// @font-face {
//   font-family: "SourceHanSansCN-Medium"; /* 字体名称 */
//   src: url("./assets/font/SourceHanSansCN-Regular.otf") format("opentype"); /* 字体文件路径和格式 */
// }

/* 在线链接服务仅供平台体验和调试使用，平台不承诺服务的稳定性，企业客户需下载字体包自行发布使用并做好备份。 */
@font-face {
  font-family: "SourceHanSansCN-Normal";font-weight: 350;src: url("//at.alicdn.com/wf/webfont/kfGqAz75vP99/lCutSI6ek6fv.woff2") format("woff2"),
  url("//at.alicdn.com/wf/webfont/kfGqAz75vP99/w4q9AZKlnk9h.woff") format("woff");
  font-display: swap;
}

/* 在线链接服务仅供平台体验和调试使用，平台不承诺服务的稳定性，企业客户需下载字体包自行发布使用并做好备份。 */
@font-face {
  font-family: "SourceHanSansCN-Bold";font-weight: 700;src: url("//at.alicdn.com/wf/webfont/kfGqAz75vP99/GxVmPra5hSl3.woff2") format("woff2"),
  url("//at.alicdn.com/wf/webfont/kfGqAz75vP99/T29qZVNyJgl2.woff") format("woff");
  font-display: swap;
}

/* 在线链接服务仅供平台体验和调试使用，平台不承诺服务的稳定性，企业客户需下载字体包自行发布使用并做好备份。 */
@font-face {
  font-family: "SourceHanSansCN-Medium";font-weight: 500;src: url("//at.alicdn.com/wf/webfont/kfGqAz75vP99/U3tkm7KayIIa.woff2") format("woff2"),
  url("//at.alicdn.com/wf/webfont/kfGqAz75vP99/8F2VmzdhCBLG.woff") format("woff");
  font-display: swap;
}
.containermixin(@fontSize,@font18,@font19,@font20,@font22,@introduceW,@titleCommonFontSize,@footerButtonSize,@footerButtonWidth,@footerButtonHeight,@footerButtonSpace,@footerHeight,@titleCommonRadius,@borderCommonMarginBottom,@borderCommonPadding,@firstContentPadding,@customGap,@boxCommonPadding,@titleCommonWidth,@titleCommonHeight,@previewBoxWidth,@previewBoxHeight,@previewBoxButtonW,@previewBoxButtonH,@explainGap,@explainFontSize,@explainImgW,@explainImgH) {
  .preview-box{
    position:fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.6);
    z-index:9999;
    display: flex;
    align-items: center;
    justify-content: center;
    &-content{
      padding: 24px;
      background: #FFFFFF;
      border-radius: 12px;
      width: @previewBoxWidth;
      height: @previewBoxHeight;
      &-title{
        font-size: 18px;
        font-family: PingFangSC-Medium, PingFang SC;
        font-weight: 500;
        color: #222226;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 5px;
        img{
          width: 12px;
          height: 12px;
          cursor:pointer;
        }
      }
      &-img-box{
        background: #CCCCD8;
        border-radius: 4px;
        padding: 10px;
        img{
          width: 362px;
          height: 392px;
        }
      }
      &-footer{
        text-align: right;
        margin-top: 28px;
        &-button{
          display: inline-block;
          width: @previewBoxButtonW;
          height: @previewBoxButtonH;
          line-height:@previewBoxButtonH;
          background: #0071FF;
          border-radius: 100px;
          color: white;
          text-align: center;
        }
      }
    }
  }
  .blue {
    color: #016ffe;
  }
  .custom-gap{
    gap:@customGap;
  }
  .gray {
    color: #999;
  }
  .border-common {
    background: #ffffff;
    box-shadow: 0px 2px 20px 0px rgba(55, 165, 202, 0.35);
    border-radius: 24px;
    padding: @borderCommonPadding;
    overflow: visible;
    margin-bottom: @borderCommonMarginBottom;
    position: relative;
    background: linear-gradient(
      180deg,
      rgba(219, 245, 255, 1),
      rgba(181, 231, 254, 1)
    );
    & > div {
      border-radius: 22px;
      background: #ffffff;
      padding: 40px 30px;
    }
  }
  .title-common {
    background: #77a1f7;
    box-shadow: 0px 6px 10px 0px rgba(120, 162, 247, 0.5);
    border-radius: @titleCommonRadius;
    font-size: @titleCommonFontSize;
    font-family: SourceHanSansCN-Bold, SourceHanSansCN;
    font-weight: bold;
    color: #ffffff;
    text-align: center;
    display: inline-block;
    position: absolute;
    left: 0;
    top: 0;
    transform: translate(0, -50%);
    width: @titleCommonWidth;
    height: @titleCommonHeight;
    line-height: @titleCommonHeight;
    background: #77A1F7;
    box-shadow: 0px 6px 10px 0px rgba(120,162,247,0.5);
    border-radius: 24px 24px 24px 0px;
  }
  .arrange-common {
    border-radius: 0px 0px 10px 10px;
    text-align: center;
    margin: 0 auto;
    padding: 15px 0;
    font-size: @font18;
  }
  .indent2f{
    // padding-left: 2*@fontSize;
    margin-bottom: 5px;
  }
  .indent4f{
    padding-left: 2*@fontSize;
    margin-bottom: 15px !important;
    &>div{
      margin-bottom: 5px;
    }
  }

  .advertise-container {
    background-image: url(./assets/banner1.png);
    background-repeat: no-repeat;
    background-position: top;
    background-color: rgba(195, 233, 255, 1);
    min-height: 100vh;
    position: relative;
    font-family: SourceHanSansCN-Normal, SourceHanSansCN;
    font-size: @fontSize;
    padding-bottom: 150px;
    -webkit-font-smoothing: antialiased;
    font-weight: normal;
    word-break: break-all;
    background-size: 2560px 800px;
    a{
      .blue;
    }
    .content {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
      padding-top: 420px;
      position: relative;
      .navigate {
        font-size: @font18;
        font-family: SourceHanSansCN-Medium, SourceHanSansCN;
        font-weight: 500;
        color: #999999;
        text-align: center;
        position: fixed;
        z-index: 99;
        right: 234px;
        top: 420px;
        border-radius: 14px;
        &-content {
          border-radius: 14px;
          padding: 10px 0;
          & > div {
            border-bottom: 1px solid #e3e3e3;
            padding: 10px;
            &>a{
              color: #999999;
            }
            &.active>a{
              .blue;
            }
            &:last-child {
              border: none;
            }
            & > a:hover {
              .blue;
            }
          }
        }
      }
      .navigate-mobile {
        position: fixed;
        display: flex;
        top: 0;
        left: 0;
        right: 0;
        border-radius: 0px 0px 12px 12px;
        background: #cbecff;
        box-shadow: 0px 2px 20px 0px rgba(55, 165, 202, 0.35);
        font-size: @font18;
        font-weight: 400;
        color: rgba(0, 0, 0, 0.5);
        flex-wrap: nowrap;
        text-align: center;
        z-index: 999;
        overflow: hidden;
        & > div {
          width: 25%;
          padding: 17px 0;
          border-right: 1px solid rgba(255, 255, 255, 0.6);
          &:last-child {
            border: none;
          }
          a>{
            color: rgba(0, 0, 0, 0.5);
          }
        }
        .active{
          &>a{
            .blue;
          }
          background: rgba(255, 255, 255, 0.6);
        }
      }
      .introduce {
        padding: @boxCommonPadding;
        &-title {
          -webkit-text-stroke: 1px #fff; /* 设置镂空效果 */
          position: absolute;
          right: 40px;
          top: 0;
          transform: translate(0, -30%);
          height: 245px;
          width: 200px;
          img{
            width: 100%;
            height: 100%;
          }
        }
        &-title-mobile {
          .title-common;
        }
        &-content {
          &-paragraph {
            text-indent: @fontSize * 2;
            margin-bottom: 10px;
          }
          &-text-box{
            padding-right: @introduceW;
          }
          &-img-box{
            img{
              width: 100%;
            }
          }
        }
      }
      .arrange {
        padding: @boxCommonPadding;
        &-title {
          .title-common;
        }
        &-content {
          &-first {
            background: #d6e3fd;
            border-radius: 10px;
            &-title {
              background-color: rgba(119, 161, 247, 0.3);
              border-radius: 10px;
              padding: 10px 20px;
              font-size: @font22;
              font-family: SourceHanSansCN-Medium, SourceHanSansCN;
              font-weight: 500;
              color: #000000;
              display: flex;
              flex-wrap: wrap;
              justify-content: space-around;
            }
            &-content {
              padding: @firstContentPadding;
              &-item {
                background: #ffffff;
                border-radius: 10px;
                text-align: center;
                padding: 10px 0;
                &-title {
                  font-size: @font20;
                  margin-bottom: 15px;
                  .blue;
                }
              }
            }
          }
          &-twice {
            .arrange-common;
            width: 80%;
            background-color: #e3ecfe;
          }
          &-third {
            .arrange-common;
            width: 60%;
            background-color: #f1f5fe;
          }
          &-fourth {
            .arrange-common;
            width: 40%;
            background-color: #f8faff;
          }
        }
      }
      .setting {
        padding: @boxCommonPadding;
        &-title {
          .title-common;
        }
        &-content {
          &-item {
            img {
              width: 100%;
              height: 100%;
            }
          }
        }
      }
      .explain{
        &-title{
          .title-common
        }
        &-content{
          &-gap{
            gap:@explainGap;
          }
          &-item{
            border-radius: 10px;
            border: 2px solid #77A1F7;
            &-img-box{
              display: flex;
              align-items: center;
              justify-content: center;
              height: 300px;
              img{
                max-width: 100%;
                max-height: 100%;
              }
            }
            &-footer{
              display: flex;
              align-items: center;
              padding: 16px 8px;
              height: 48px;
              background: #77A1F7;
              box-shadow: 0px 6px 10px 0px rgba(120,162,247,0.5);
              font-size: @explainFontSize;
              font-family: SourceHanSansCN-Medium, SourceHanSansCN;
              font-weight: 500;
              color: #FFFFFF;
              border-radius: 0 0 5px 5px;
              img{
                margin-right: 8px;
                width: @explainImgW;
                height: @explainImgH;
                border: 1px solid #FFFFFF;
                border-radius: 16px;
              }
            }
          }
        }
        
      }
      .flow {
        padding: @boxCommonPadding;
        .qr-box{
          position: relative;
          display: inline-block;
          >span{
            position: absolute;
            display: inline-block;
            width: 156px;
            height: 185px;
            padding: 10px;
            bottom: 0;
            left: 50%;
            transform: translate(-50%,100%);
            background: #fff;
            text-align: center;
            box-shadow: 0px 2px 12px 0px rgba(0,0,0,0.06);
            border-radius: 2px;
            border: 1px solid #E4E7ED;
            img{
              width: 100%;
              display: block;
            }
          }
        }
        .robot-logo{
          width: 32px !important;
          height: 32px !important;
          display: inline-block;
          margin-right: 2px;
          transform: translate(0,-3px);
        }
        .qr-box-mobile{
          position:fixed;
          top: 0;
          bottom: 0;
          left: 0;
          right: 0;
          background: rgba(0, 0, 0, 0.6);
          z-index:9999;
          display: flex;
          align-items: center;
          justify-content: center;
          &-content{
            width: 280px;
            height: 302px;
            background: #FFFFFF;
            border-radius: 12px;
            &-title{
              font-size: 18px;
              font-family: PingFangSC-Medium, PingFang SC;
              font-weight: 500;
              color: #2774E9;
              width:100%;
              text-align: center;
              margin-top: 24px;
              margin-bottom: 22px;
            }
            >img{
              width: 140px;
              height: 140px;
              margin: 0 auto;
              margin-bottom: 24px;
            }
            &-button{
              width: 232px;
              height: 42px;
              line-height: 42px;
              background: #0071FF;
              border-radius: 21px;
              color:white;
              font-size:16px;
              text-align:center;
              margin: 0 auto;
            }
          }
        }
        &-title {
          .title-common;
        }
        &-content {
          &-step-title{
            font-size: @font18;
            font-family: SourceHanSansCN-Medium, SourceHanSansCN;
            font-weight: 500;
            color: #000000;
          }
          &-title {
            font-family: SourceHanSansCN-Normal, SourceHanSansCN;
            font-weight: 500;
          }
          &-blue {
            .blue;
            font-size: @font18;
          }
        }
      }
    }
    .footer {
      width: 100%;
      height: @footerHeight;
      background: #ffffff;
      box-shadow: 0px 2px 20px 0px rgba(55, 165, 202, 0.35);
      border-radius: 24px 24px 0px 0px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: fixed;
      bottom: 0;
      z-index: 100;
      &-button {
        background: linear-gradient(180deg, #afcffc 0%, #3a7bff 100%);
        box-shadow: 0px 6px 10px 0px rgba(120, 162, 247, 0.5);
        border-radius: 32px;
        font-family: SourceHanSansCN-Bold, SourceHanSansCN;
        font-weight: bold;
        color: #ffffff;
        font-size: @footerButtonSize;
        width: @footerButtonWidth;
        height: @footerButtonHeight;
        line-height: @footerButtonHeight;
        margin-right:@footerButtonSpace;
        text-align: center;
        cursor: pointer;
        a{
          color: white !important;
          display: block;
          width: 100%;
          height: 100%;
        }
        &:last-child{
          margin-right: 0 !important;
        }
      }
    }
  }
}

@media screen and (min-width: 1200px) {
  @fontSize: 14px; //基本字体大小
  @font18: 18px; //较大内容字体大小
  @font19: 19px; //最大内容字体大小
  @font20: 20px; //小title字体大小
  @font22: 22px; //中title字体大小
  @introduceW: 220px; //活动结束宽度
  @titleCommonFontSize: 24px; //浮层标题字体大小
  @footerButtonSize:20px;
  @footerButtonWidth:240px;
  @footerButtonHeight:56px;
  @footerButtonSpace:56px;
  @footerHeight:90px;
  @titleCommonRadius:26px;
  @borderCommonMarginBottom:80px;
  @borderCommonPadding:10px;
  @firstContentPadding:20px;
  @customGap:20px;
  @boxCommonPadding:40px 30px;
  @titleCommonWidth:172px;
  @titleCommonHeight:56px;
  @previewBoxWidth:430px;
  @previewBoxHeight:550px;
  @previewBoxButtonW:96px;
  @previewBoxButtonH:32px;
  @explainGap:24px;
  @explainFontSize:16px;
  @explainImgW:32px;
  @explainImgH:32px;
  .containermixin(@fontSize,@font18,@font19,@font20,@font22,@introduceW,@titleCommonFontSize,@footerButtonSize,@footerButtonWidth,@footerButtonHeight,@footerButtonSpace,@footerHeight,@titleCommonRadius,@borderCommonMarginBottom,@borderCommonPadding,@firstContentPadding,@customGap,@boxCommonPadding,@titleCommonWidth,@titleCommonHeight,@previewBoxWidth,@previewBoxHeight,@previewBoxButtonW,@previewBoxButtonH,@explainGap,@explainFontSize,@explainImgW,@explainImgH);
  .advertise-container .content .setting .annotation-line:last-child{
    padding-left: 28px;
  }
}
@media screen and (max-width: 1200px) {
  @fontSize:14px; //基本字体大小
  @font18:15px; //较大内容字体大小
  @font19:19px; //最大内容字体大小
  @font20:16px; //小title字体大小
  @font22:14px; //中title字体大小
  @introduceW:0; //活动结束宽度
  @titleCommonFontSize:20px; //浮层标题字体大小
  @footerButtonSize:16px;
  @footerButtonWidth:162px;
  @footerButtonHeight:40px;
  @footerButtonSpace:24px;
  @footerHeight:64px;
  @titleCommonRadius:24px;
  @borderCommonMarginBottom:45px;
  @borderCommonPadding:6px;
  @firstContentPadding:10px;
  @customGap:11px;
  @boxCommonPadding:40px 10px;
  @titleCommonWidth:116px;
  @titleCommonHeight:40px;
  @previewBoxWidth:280px;
  @previewBoxHeight:419px;
  @previewBoxButtonW:232px;
  @previewBoxButtonH:42px;
  @explainGap:15px;
  @explainFontSize:14px;
  @explainImgW:20px;
  @explainImgH:20px;
  .containermixin(@fontSize,@font18,@font19,@font20,@font22,@introduceW,@titleCommonFontSize,@footerButtonSize,@footerButtonWidth,@footerButtonHeight,@footerButtonSpace,@footerHeight,@titleCommonRadius,@borderCommonMarginBottom,@borderCommonPadding,@firstContentPadding,@customGap,@boxCommonPadding,@titleCommonWidth,@titleCommonHeight,@previewBoxWidth,@previewBoxHeight,@previewBoxButtonW,@previewBoxButtonH,@explainGap,@explainFontSize,@explainImgW,@explainImgH);
  .advertise-container .content .arrange{
    padding:40px 10px;
  }
  .advertise-container .content .introduce{
    padding-bottom: 20px;
  }
  .advertise-container .content .setting .annotation-line:last-child{
    padding-left: 0px;
  }
}

@media screen and (max-width: 1100px) {
  .advertise-container {
    background-image: url(https://csdn-665-inscode.s3.cn-north-1.jdcloud-oss.com/act/banner_mobile.png/large);
    background-size: contain;
  }
  .advertise-container .content {
    padding-top: 72%;
  }
}
</style>
