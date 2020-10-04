define("appmsg/emotion/emotion.js",["appmsg/emotion/dom.js","appmsg/emotion/slide.js","appmsg/emotion/common.js","appmsg/emotion/nav.js","appmsg/emotion/textarea.js","biz_common/utils/emoji_data.js","biz_common/utils/emoji_panel_data.js","biz_common/dom/class.js"],function(t,n){
"use strict";
function e(){
v.WIDTH=y=_("#js_article").width()||_("#js_cmt_mine").width(),v.pageCount=k=i(),
o(),a(),s();
}
function i(){
u=y-2*P,S=parseInt(u/W),M=3*S-1;
var t=parseInt(R/M);
return R%M!==0&&t++,t;
}
function o(){
var t=_("#js_slide_wrapper"),n=v.wrapperWidth=k*y;
t.css({
width:n+"px"
});
}
function a(){
for(var t=_("#js_slide_wrapper").el[0],n=(y-S*W)/2,e=0,i=k;i>e;e++){
var o=document.createElement("ul");
o.setAttribute("class","emotion_list"),t.appendChild(o),_(o).css({
width:y+"px",
"float":"left",
"padding-left":n+"px",
"padding-right":"0"
}),c(o,e,n);
}
}
function s(){
for(var t=_("#js_navbar"),n=0,e=k;e>n;n++){
var i=_(_.el("li"));
i.attr("class","emotion_nav js_emotion_nav"),D.push(i),t.append(i);
}
v.navs=D;
}
function c(t,n,e){
for(var i=0,o=M;o>i;i++){
var a=document.createElement("li");
if(A++,A>R)break;
a=r(A),_(t).append(a);
}
var s=m(e);
_(t).append(s);
}
function r(t){
var n=_(_.el("li")),e=_(_.el("i")),i=0;
e.attr("class","icon_emotion icon"+t),e.css({
"background-position":"0px "+((1-t)*Z-i)+"px"
}),n.attr("class","emotion_item js_emotion_item"),n.attr("data-index",t);
var o=W+"px";
return n.css({
width:o,
height:o
}),n.append(e),n;
}
function m(t){
var n=_(_.el("li")),e=_(_.el("i"));
n.attr("class","emotion_item del js_emotion_item"),n.attr("data-index",-1),e.attr("class","icon_emotion del");
var i=W+"px";
return n.css({
width:i,
height:i,
right:t+"px"
}),n.append(e),n;
}
function l(){
function t(){
o.show(),w.show(),i.blur(),_.later(function(){
i.blur();
});
}
function n(){
o.hide(),w.hide(),i.focus(),_.later(function(){
i.focus();
});
}
w=_("#js_emotion_panel");
var e=_("#js_cmt_input"),i=e.el[0],o=_("#js_emotion_panel_arrow_wrp"),a=document.getElementById("js_emotion_switch"),s="emotion_switch_current";
w.hide(),_("#js_emotion_switch").on("tap",function(e){
console.log("emotion click"),e.preventDefault(),e.stopPropagation(),g=!g,g?(t(),
E.addClass(a,s)):(n(),E.removeClass(a,s));
}),e.on("tap",function(){
w.hide(),g=!1;
});
}
function p(){
function t(t){
if(!v.isMoved){
var n=_(t.currentTarget),e=+n.attr("data-index");
h.inputEmotion(e);
}
}
_("li.js_emotion_item").on("click",t),_("li.js_emotion_item").on("touchend",t);
}
function d(t){
for(var n=[],e=0;e<x.length;e++){
var i=x[e];
if(i.cn){
var o=new RegExp(i.cn.replace("[","\\[").replace("]","\\]"),"g"),a=t.match(o);
a&&(n=n.concat(a));
}
if(i.emoji){
var o=new RegExp(i.emoji,"g"),a=t.match(o);
a&&(n=n.concat(a));
}
}
return _.each(n,function(n){
if(void 0!==O[n]){
var e=O[n],i=z[e],o='<i class="icon_emotion_single '+i+'"></i>';
t=t.replace(n,o);
}
}),t;
}
for(var u,_=t("appmsg/emotion/dom.js"),f=t("appmsg/emotion/slide.js"),v=t("appmsg/emotion/common.js"),j=t("appmsg/emotion/nav.js"),h=t("appmsg/emotion/textarea.js"),n=(_.each,
{}),g=!1,w=null,x=t("biz_common/utils/emoji_data.js"),b=t("biz_common/utils/emoji_panel_data.js"),E=t("biz_common/dom/class.js"),I={},O={},z=[],T=0;T<x.length;T++){
var C=x[T];
I[C.id]=C;
}
for(var T=0;T<b.length;T++){
var N=b[T],C=I[N];
O[C.cn]=T,C.emoji&&(O[C.emoji]=T),z.push(C.style);
}
var k,M,S,y,D=[],P=15,R=v.EMOTIONS_COUNT,W=v.EMOTION_LI_SIZE,Z=v.EMOTION_SIZE;
n.init=function(){
l(),e(),f.init(),j.activeNav(0),p(),h.init();
};
var A=0;
return n.encode=function(t){
t=d(t);
var n=/\/([\u4e00-\u9fa5\w]{1,4})/g,e=t.match(n);
return e?(_.each(e,function(n){
var e=n.replace("/",""),i=[e.slice(0,4),e.slice(0,3),e.slice(0,2),e.slice(0,1)];
_.each(i,function(n){
if(void 0!==O["["+n+"]"]){
var e=O["["+n+"]"],i=z[e],o='<i class="icon_emotion_single '+i+'"></i>';
t=t.replace("/"+n,o);
}
});
}),t):t;
},n.hidePannel=function(){
w.hide();
},n;
});define("biz_common/utils/report.js",[],function(){
"use strict";
return function(n){
var e=new Image;
e.src=n;
};
});define("appmsg/articleReport.js",["biz_common/utils/string/html.js","biz_common/dom/event.js","biz_wap/utils/mmversion.js"],function(i){
"use strict";
function n(i){
i.dom&&(i.dom.style.display="",t.tap(i.dom,function(){
var n=["https://mp.weixin.qq.com/mp/infringement?url=",encodeURIComponent(i.link.htmlDecode()),"&title=",encodeURIComponent(i.title),"&__biz=",window.biz].join("");
return location.href=n+"#wechat_redirect",!1;
}));
}
i("biz_common/utils/string/html.js");
{
var t=i("biz_common/dom/event.js"),e=i("biz_wap/utils/mmversion.js");
({
not_in_mm:!e.isWp&&-1==navigator.userAgent.indexOf("MicroMessenger")
});
}
return{
init:n
};
});define("appmsg/topic_tpl.html.js",[],function(){
return'<span class="db topic_wrp">\n    <span class="topic_thumb" style="background-image:url({img_url});"></span>\n    <span class="topic_content">\n        <strong class="topic_title">{title}</strong>\n        <span class="topic_desc">{author}</span>\n        <span class="topic_info">\n            <span class="topic_info_extra"><span class="icon_topic"></span>话题</span>\n            <span class="topic_info_primary">相关文章{msg_num}篇</span>\n        </span>\n    </span>\n</span>\n';
});define("pages/utils.js",["appmsg/appmsg_report.js","biz_common/utils/emoji_data.js","pages/version4video.js","biz_wap/utils/mmversion.js","biz_wap/jsapi/core.js","biz_common/dom/event.js","common/utils.js"],function(e){
"use strict";
function t(e){
if(!e)return null;
var t=location.href.match(new RegExp("(\\?|&)"+e+"=([^&]+)"));
return t?t[2]:null;
}
function n(e){
if(window.hasChannelTwoTab&&v.isNewNativePage()){
var t=void 0;
t=document.getElementById("tab").offsetTop-window.minHeight;
var n=document.body.offsetHeight,o=v.getInnerHeight()+t;
if(o>n){
var i=t+v.getInnerHeight()-document.body.offsetHeight,a=document.createElement("div");
a.setAttribute("class","empty_comment_element"),a.style.cssText="height: "+i+"px;",
document.getElementById(e).appendChild(a);
}
window.minMountHeight=o;
}
}
function o(e){
for(var t=window.location.href,n=t.indexOf("?"),o=t.substr(n+1),i=o.split("&"),a=0;a<i.length;a++){
var r=i[a].split("=");
if(r[0].toUpperCase()==e.toUpperCase())return r[1];
}
return"";
}
function i(e,t){
g.invoke("createWebViewForFastLoad",{
scene:1
},function(){
e.forEach(function(e){
g.invoke("downloadPageDataForFastLoad",{
itemList:[{
item_show_type:5,
url:e[t]
}]
},function(e){
console.log(e);
});
});
});
}
function a(e,t,n){
var o=void 0;
return function(){
var i=this,a=arguments,r=function(){
o=null,n||e.apply(i,a);
},c=n&&!o;
clearTimeout(o),o=setTimeout(r,t),c&&e.apply(i,a);
};
}
function r(e){
var t=parseInt(e,10),n=0,o=0;
t>60&&(n=parseInt(t/60,10),t=parseInt(t%60,10),n>60&&(o=parseInt(n/60,10),n=parseInt(n%60,10))),
10>t&&(t="0"+t);
var i=":"+t;
return n>0?(10>n&&(n="0"+n),i=n+i):i="00"+i,o>0&&(0===parseInt(o,10)?o="":10>o&&(o="0"+o),
i=""+o+":"+i),i;
}
function c(e){
var t="";
if(parseInt(e,10)>1e5)t="10万+";else if(parseInt(e,10)>1e4&&parseInt(e,10)<=1e5){
var n=""+parseInt(e,10)/1e4,o=n.indexOf(".");
t=-1===o?n+"万":n.substr(0,o)+"."+n.charAt(o+1)+"万";
}else t=0===parseInt(e,10)?"":e;
return t;
}
function s(e,t){
var n=void 0,o=void 0;
return function(){
var i=this,a=arguments,r=+new Date;
n&&n+t>r?(clearTimeout(o),o=setTimeout(function(){
n=r,e.apply(i,a);
},t)):(n=r,e.apply(i,a));
};
}
function m(){
var e=0,t=0,n=0;
return document.body&&(t=document.body.scrollTop),document.documentElement&&(n=document.documentElement.scrollTop),
e=t-n>0?t:n;
}
function u(){
var e=0,t=void 0,n=void 0;
return document.body&&(t=document.body.scrollHeight),document.documentElement&&(n=document.documentElement.scrollHeight),
e=t-n>0?t:n;
}
function l(){
var e=0;
return e="CSS1Compat"===document.compatMode?document.documentElement.clientHeight:document.body.clientHeight;
}
var p=e("appmsg/appmsg_report.js"),d=e("biz_common/utils/emoji_data.js"),f=e("pages/version4video.js"),h=e("biz_wap/utils/mmversion.js"),g=e("biz_wap/jsapi/core.js"),w=e("biz_common/dom/event.js"),v=e("common/utils.js"),_={
inWechat:f.device.inWechat,
windowWechat:/WindowsWechat/i.test(navigator.userAgent),
macWechat:/wechat.*mac os/i.test(navigator.userAgent),
emojiImg:'<img src="https://res.wx.qq.com/mpres/zh_CN/htmledition/comm_htmledition/images/pic/common/pic_blank.gif" class="icon_emotion_single #style#" alt="#name#">',
emojiDataMap:{}
};
!function(){
for(var e=0,t=d.length;t>e;e++){
var n=d[e];
n.cn&&!_.emojiDataMap[n.cn]&&(_.emojiDataMap[n.cn]={
index:e
}),n.hk&&!_.emojiDataMap[n.hk]&&(_.emojiDataMap[n.hk]={
index:e
}),n.us&&!_.emojiDataMap[n.us]&&(_.emojiDataMap[n.us]={
index:e
});
}
}();
var b=function(e){
return/\[[^\[\]]+\]/.test(e)?e.replace(/\[[^\[\]]+\]/g,function(e){
if(_.emojiDataMap[e]&&d[_.emojiDataMap[e].index]){
var t=d[_.emojiDataMap[e].index];
return _.emojiImg.replace("#name#",e).replace("#style#",t.style);
}
return e;
}):e;
},j=function(e,t){
_.inWechat?_.windowWechat||_.macWechat?t===!0?window.parent.open(e):window.parent.location.href=e:g.invoke("openUrlWithExtraWebview",{
url:e,
openType:1
},function(n){
-1==n.err_msg.indexOf("ok")&&(t===!0?window.parent.open(e):window.parent.location.href=e);
}):t===!0?window.open(e):location.href=e;
},y=function(){
!_.inWechat||_.windowWechat||_.macWechat?window.close():g.invoke("closeWindow",function(e){
-1==e.err_msg.indexOf("ok")&&window.close();
});
},W=function(e){
return document.getElementById(e);
},I=function(e){
return document.getElementsByClassName(e);
},x=function(e){
return e.replace(/^\s+|\s+$/g,"");
},k=function(e,t){
return(t||document).querySelector(e);
},T=function(e,t){
return(t||document).querySelectorAll(e);
},E=function(e){
var n=e.$container;
n&&!h.isInMiniProgram&&w.on(n,"tap",".js_go_profile",function(n){
var o=n.delegatedTarget;
o&&!function(){
var n=o.getAttribute("data-biz")||e.biz||window.biz||"";
if("function"==typeof e.beforeGo2Profile&&e.beforeGo2Profile(o),1==window.isprofileblock)g.invoke("openUrlWithExtraWebview",{
url:"https://mp.weixin.qq.com/mp/profileblock?__biz="+n+"#wechat_redirect",
openType:1
},function(e){
-1==e.err_msg.indexOf("ok")&&(location.href="https://mp.weixin.qq.com/mp/profileblock?__biz="+n+"#wechat_redirect");
});else{
var i=o.getAttribute("data-scene")||e.profile_scene||"";
p.profileReport({
isnew:0,
title:e.title||"",
item_show_type:e.item_show_type||""
}),console.log("channelSessionId"+t("channel_session_id")),g.invoke("profile",{
username:e.user_name,
profileReportInfo:"",
scene:i,
channelSessionId:t("channel_session_id")
},function(){});
}
}();
});
};
return{
jumpUrl:j,
closeWin:y,
trim:x,
getId:W,
qs:k,
qsAll:T,
inWechat:_.inWechat,
windowWechat:_.windowWechat,
macWechat:_.macWechat,
emojiFormat:b,
getParam:t,
go2ProfileEvent:E,
prepareNativePage:i,
debounce:a,
throttle:s,
formatReadNum:c,
formatSeconds:r,
setTwoTabHeight:n,
getByClass:I,
getScrollTop:m,
getScrollHeight:u,
getWindowHeight:l,
getQuery:o
};
});function _typeof(e){
return e&&"undefined"!=typeof Symbol&&e.constructor===Symbol?"symbol":typeof e;
}
define("question_answer/utils.js",["biz_common/utils/string/html.js","pages/utils.js","biz_wap/jsapi/core.js","appmsg/log.js","biz_wap/utils/mmversion.js","biz_common/dom/event.js"],function(e){
"use strict";
e("biz_common/utils/string/html.js");
var t=e("pages/utils.js"),i=e("biz_wap/jsapi/core.js"),o=e("appmsg/log.js"),r=e("biz_wap/utils/mmversion.js"),n=e("biz_common/dom/event.js"),a={
classPrefix:window.qaClassPrefix,
previewFlag:!1
},s=function(e,t){
var i=new Date(1e3*e),o=e-t,r=i.getFullYear(),n=1*t,a=new Date(1e3*n);
i.setHours(0),i.setMinutes(0),i.setSeconds(0);
var s=i.getTime()/1e3;
return n>=s?3600>o?Math.ceil(o/60)+"分钟前":"今天":n>=s-86400?"昨天":n>=s-172800?"前天":a.getFullYear()===r?a.getMonth()+1+"月"+a.getDate()+"日":a.getFullYear()+"年"+(a.getMonth()+1)+"月"+a.getDate()+"日";
},l=function(e,i,o){
if(i=i||Math.ceil((new Date).getTime()/1e3),1*o===1&&e.question){
var r=e.question;
e.biz_nickname=r.biz_nickname||"匿名",e.elected_comment_num=r.elected_comment_num||0,
e.like_num=r.like_num||0;
var n=r.question_info;
e.question_page_url=c(r.question_page_url.html(!1)),e.questioner_useruin=n.questioner_useruin,
e.qa_id=n.qa_id,n.question&&(n.question.ask_time_str=s(i,n.question.ask_timestamp),
e.questionTitle=n.question.title.html(!0).replace(/\r/g,"").replace(/\n/g,"<br>").replace(/\s/g,"&nbsp;"),
e.questionTitle=t.emojiFormat(n.question.title));
}else if(1*o===2&&e.topic){
var a=e.topic;
e.useful_num=a.useful_num||0,e.elected_comment_num=a.elected_comment_num||0,e.topicName=a.topic&&a.topic.wording||"暂无主题",
e.topicId=a.topic&&a.topic.id||1,e.biz_nickname=a.biz_nickname||"",e.biz_headimg=a.biz_headimg||"https://mmbiz.qpic.cn/mmbiz_png/cVgP5bCElFjtIK2EeF0OjuGhbZVFRYyGRfbFeZ9GibWsibibIWP7XRSKews1ibWFZD5biaSXb7HfMF6dMricUib4naAFw/0";
}else if(1*o===3&&e.list){
var l=e.list;
e.useful_num=l.useful_num||0,e.total_num=l.total_num||0,e.biz_nickname=l.biz_nickname||"",
e.biz_headimg=l.biz_headimg||"https://mmbiz.qpic.cn/mmbiz_png/cVgP5bCElFjtIK2EeF0OjuGhbZVFRYyGRfbFeZ9GibWsibibIWP7XRSKews1ibWFZD5biaSXb7HfMF6dMricUib4naAFw/0";
}
return e;
},u=function(e){
if(!a.previewFlag){
a.previewFlag=!0,"undefined"==typeof window.getComputedStyle&&(window.getComputedStyle=document.body.currentStyle?function(e){
return e.currentStyle;
}:{});
var t={
current:e.curUrl,
urls:e.imgsSrc,
currentInfo:{
url:e.curUrl,
data:""
}
},n=e.dataUrlDom,s="";
if(n){
var l=window.getComputedStyle(n),u=document.createElement("canvas");
u.style.width=l.width,u.style.height=l.height,u.width=parseFloat(l.width),u.height=parseFloat(l.height);
var m=u.getContext("2d");
if(!r.isAndroid)try{
m.drawImage(n,0,0,parseFloat(l.width),parseFloat(l.height)),s=u.toDataURL();
}catch(c){
s="";
}
s&&(t.currentInfo.data=s);
}
var p=null;
if(e.posDom){
var d=window.getComputedStyle(e.posDom),g=e.posDom.getBoundingClientRect();
p={
x:g.left-parseFloat(d.paddingLeft)-parseFloat(d.borderLeftWidth),
y:g.top-parseFloat(d.paddingTop)-parseFloat(d.borderTopWidth),
width:g.width-parseFloat(d.paddingLeft)-parseFloat(d.paddingRight)-parseFloat(d.borderLeftWidth)-parseFloat(d.borderRightWidth),
height:g.height-parseFloat(d.paddingTop)-parseFloat(d.paddingBottom)-parseFloat(d.borderTopWidth)-parseFloat(d.borderBottomWidth)
},t.currentInfo.pos=p;
}
i.invoke("imagePreview",t,function(t){
console.log("imagePreview response",t),window.__addIdKeyReport&&e.reportId&&e.reportKey&&window.__addIdKeyReport(e.reportId,e.reportKey);
}),setTimeout(function(){
a.previewFlag=!1;
},500),o("[questionAnswer] click image, src: "+e.curUrl);
}
},m=function(e){
var t="."+a.classPrefix+"preview_js";
e.container.querySelectorAll(t).forEach(function(t){
!function(i){
n.on(i,"click",function(){
var o=null;
o="img"===i.nodeName.toLocaleLowerCase()&&i.className.indexOf("qa__preview_base64_js")>=0?i:i.querySelector("img.qa__preview_base64_js"),
u({
curUrl:i.getAttribute("data-src"),
dataUrlDom:o,
imgsSrc:e.imgsSrc,
posDom:t,
reportId:e.jsapiReportId,
reportKey:e.jsapiReportKey
});
});
}(t);
});
},c=function(e){
return e.replace("#rd","#wechat_redirect").replace(/^http:\/\//,"https://");
};
return{
formatQuestionInfo:l,
formatCreateTime:s,
classPrefix:a.classPrefix,
bindReviewImageEvent:m,
formatPageUrl:c,
reviewImage:u
};
});define("question_answer/appmsg_tpl.html.js",[],function(){
return'<#if(type==1){#>\n<div class="qa__card qa__show_detail_js" data-key="<#=dataKey#>">\n  <#if(dataStatus==3||dataStatus==4){#>\n    <section class="qa__card-empty">\n      <#if(dataStatus==4){#>\n      该问答内容已被删除      <#}else{#>\n      问答内容加载失败      <#}#>\n    </section>\n  <#}else if(dataStatus==2){#>\n    <div class="qa__card-hd"><span><#=biz_nickname#></span>回答了提问</div>\n    <div class="qa__card-bd">\n      <#if(question.question_info.question){#>\n      <div class="qa__card-desc">\n        <#==questionTitle#>\n      </div>\n      <#}#>\n    </div>\n    <div class="qa__card-ft">\n      <span><#=like_num#>有用</span>\n      <span><#=elected_comment_num#>评论</span>\n    </div>\n  <#}#>\n</div>\n<#}else if(type==2){#>\n<div class="qa__card qa__card_v2 qa__show_theme_js" data-key="<#=dataKey#>">\n  <div class="weui-btn weui-btn_primary qa__btn"><i class="qa__icon-qa"></i>向我提问</div>\n  <div class="qa__card-hd"><span><#=biz_nickname#></span>发布了一个主题</div>\n  <div class="qa__card-bd">\n    <div class="qa__card-theme"><#=topicName#></div>\n  </div>\n  <div class="qa__card-ft">\n    <span><#=useful_num#>有用</span>\n    <span><#=elected_comment_num#>评论</span>\n  </div>\n</div>\n<#}else if(type==3){#>\n<div class="qa__card qa__card_v3 qa__show_profile_js" data-key="<#=dataKey#>">\n  <div class="weui-btn weui-btn_primary qa__btn"><i class="qa__icon-qa"></i>向我提问</div>\n  <div class="qa__card-bd">\n    <div class="qa__card-content">\n      <div class="qa__card-avatar">\n        <img src="<#=biz_headimg#>" alt="">\n      </div>\n      <div class="qa__card-main">\n        <div class="qa__card-main-name"><#=biz_nickname#></div>\n        <div class="qa__card-main-info"><span><#=total_num#>个回答</span><br><span><#=useful_num#>次有用</span></div>\n      </div>\n    </div>\n  </div>\n</div>\n<#}#>';
});define("pages/weapp_tpl.html.js",[],function(){
return'<span class="weapp_card app_context pages_reset appmsg_card_context appmsg_card_active">\n    <span class="weapp_card_bd">\n        <span class="weapp_card_profile flex_context">\n            <span class="radius_avatar weapp_card_avatar">\n                <img src="<#=avatar#>">\n            </span>\n            <span class="flex_bd">\n              <span class="weapp_card_nickname_wrp">\n                <span class="guarantee_icon">交易担保</span>\n                <span class="weapp_card_nickname"><#=nickname#></span>\n              </span>\n            </span>\n        </span>\n        <span class="weapp_card_info">\n            <span class="weapp_card_title"><#=title#></span>\n            <span class="weapp_card_thumb_wrp" style="background-image:url(<#=imageUrl#>);"></span>\n        </span>\n    </span>\n    <span class="weapp_card_ft">\n        <span class="weapp_card_logo">小程序</span>\n    </span>\n</span>\n';
});define("biz_common/utils/monitor.js",[],function(){
"use strict";
var n=[],t={};
return t.setAvg=function(r,e,i){
return n.push(r+"_"+e+"_"+i),n.push(r+"_"+(e-1)+"_1"),t;
},t.setSum=function(r,e,i){
return n.push(r+"_"+e+"_"+i),t;
},t.send=function(){
if(0!=n.length){
var t=[];
for(t.push(n.splice(0,60));n.length>0;)t.push(n.splice(0,60));
n=[];
for(var r=0,e=t.length;e>r;r++){
var i=new Image;
i.src="//mp.weixin.qq.com/mp/jsmonitor?idkey="+t[r].join(";")+"&t="+Math.random();
}
}
},t.getData=function(t){
t=t||{};
var r=[];
try{
r=JSON.parse(JSON.stringify(n));
}catch(e){
r=[];
}
return t.remove!==!1&&(n=[]),r;
},t;
});define("pages/player_tips.js",["biz_common/tmpl.js","pages/audition_tpl.html.js","biz_common/dom/event.js"],function(t){
"use strict";
function i(t){
this.parent=document.body,this.opt=t||{},this.init();
}
var n=t("biz_common/tmpl.js"),e=t("pages/audition_tpl.html.js"),o=t("biz_common/dom/event.js");
return i.prototype.init=function(){
var t=document.createElement("div");
t.innerHTML=n.tmpl(e,this.opt),this.parent.appendChild(t),this.dom=document.getElementById("js_music_dialog");
var i=this;
o.on(i.dom.getElementsByClassName("js_submit")[0],"click",function(){
i.parent.removeChild(t),"function"==typeof i.opt.onClick&&i.opt.onClick();
});
},i;
});define("redpackage/tpl/card_tpl.html.js",[],function(){
return'<#if(!isUpdate){#>\n<section class="js_wap_redpacketcover red_package_cover_wrp" data-coveruri="<#=data.cover_uri#>">\n<#}#>\n    <!--不可操作，这里加className point_event_no-->\n    <!--todo 加载中加className red_package_cover__inner__loading-->\n    <section class="red_package_cover__inner">\n        <section class="red_package_cover__inner__main">\n            <section class="red_package_cover__body">\n                <!--图片没加载处理，这里加className red_package_cover_img_loading-->\n                <span class="red_package_cover_img" style="background-image: url(\'<#=data.receive_image#>\');"></span>\n            </section>\n            <section class="red_package_cover__foot">\n                <#if(data.status * 1===0){#>\n                <span class="red_package_cover__access-link">领取<#=data.name#>红包封面</span>\n                <#}else if(data.status * 1===1){#>\n                <span class="red_package_cover__access-link disabled">已领取红包封面</span>\n                <#}else if(data.status * 1===2){#>\n                <span class="red_package_cover__access-link disabled">红包封面已领取完</span>\n                <#}else{#>\n                <span class="red_package_cover__access-link disabled">红包封面不可领取</span>\n                <#}#>\n            </section>\n        </section>\n        <section class="red_package_cover__extend">\n            <span class="red_package_cover__extend_icon"></span>\n            <span class="red_package_cover__extend_info">微信红包封面</span>\n        </section>\n    </section>\n<#if(!isUpdate){#>\n</section>\n<#}#>';
});define("pages/voice_tpl.html.js",[],function(){
return'<span class="js_audio_frame db pages_reset audio_area">\n    <#if(show_not_support===true){#>\n    <span class="db">当前浏览器不支持播放音乐或语音，请在微信或其他浏览器中播放</span>\n    <#}#>\n    <span aria-labelledby="语音" id="voice_main_<#=voiceid#>_<#=posIndex#>" class="appmsg_card_context appmsg_card_active db audio_card" <#if(!musicSupport){#>style="display:none;"<#}#>>\n      <strong id="voice_title_<#=voiceid#>_<#=posIndex#>" class="audio_card_title" aria-describedby="语音标题" role="link"><#=title#></strong>\n\n      <#if(!!nickname){#>\n      <span id="voice_author_<#=voiceid#>_<#=posIndex#>" class="audio_card_desc">来自<#=nickname#></span>\n      <#}#>\n      <span class="weui-flex">\n        <span class="weui-flex__item">\n          <span class="audio_card_opr">\n            <span id="voice_seekRange_<#=voiceid#>_<#=posIndex#>" class="audio_card_progress_wrp">\n              <span class="audio_card_progress">\n                <span id="voice_progress_<#=voiceid#>_<#=posIndex#>" style="width:0%" class="audio_card_progress_inner"></span>\n                <span id="voice_buffer_<#=voiceid#>_<#=posIndex#>" class="audio_card_progress_buffer" style="width:0%;"></span>\n                <span id="voice_loading_<#=voiceid#>_<#=posIndex#>" class="audio_card_progress_loading" style="display:none;"></span>\n              </span>\n              <span id="voice_playdot_<#=voiceid#>_<#=posIndex#>" class="audio_card_progress_handle" style="display:none;left:0%;"></span>\n            </span>\n            <span class="audio_card_tips" aria-labelledby="时长">\n              <em id="voice_playtime_<#=voiceid#>_<#=posIndex#>" class="audio_card_length_current" aria-hidden="true">00:00</em>\n              <em id="voice_duration_<#=voiceid#>_<#=posIndex#>" class="audio_card_length_total"><#=duration_str#></em>\n            </span>\n          </span>\n        </span>\n        <span id="voice_play_<#=voiceid#>_<#=posIndex#>" aria-labelledby="播放开关" class="audio_card_switch"><em class="weui-audio-btn" role="button"></em></span>\n      </span>\n    </span>\n</span>\n\n';
});define("pages/kugoumusic_ctrl.js",["biz_common/utils/monitor.js","biz_wap/utils/ajax.js","pages/musicUrlReport.js"],function(e){
"use strict";
function r(e,r){
for(var t,a=[/^http(s)?:\/\/singerimg\.kugou\.com([\/?].*)*$/i,/^http(s)?:\/\/imge\.kugou\.com([\/?].*)*$/i],o=!1,s=0;t=a[s++];)if(t.test(e.albumurl)){
o=!0;
break;
}
return o||(e.albumurl=""),e.detailUrl="https://m3ws.kugou.com/kgsong/"+e.jumpurlkey+".html?fromweixin=",
e.webUrl=e.detailUrl,e.musicIcon=n.musicIcon,e.media_id=e.musicid,e.type=1*r.scene===0?5:1*r.scene===1?6:9,
e;
}
function t(e,r){
var t=e,a=t.otherid+(t.albumid||""),s=n.cache[a];
return s&&"function"==typeof r.callback?void r.callback(s):void(n.submiting[a]!==!0&&(n.submiting[a]=!0,
o({
jumpurlkey:t.jumpurlkey,
songId:t.songId,
akey:t.otherid,
albumid:t.albumid||"",
onSuc:function(e){
n.submiting[a]=!1,n.cache[a]=e,"function"==typeof r.callback&&r.callback(e);
},
onError:function(){
n.submiting[a]=!1,"function"==typeof r.callback&&r.callback({
canplay:!1,
msg:"系统繁忙，请稍后再试。返回码：-1",
status:-1,
play_url:"",
duration:0
});
}
})));
}
function a(e){
var r=!0,t="";
switch(1*e){
case 0:
r=!0;
break;

case 1:
r=!1,t="该歌曲版权已过期，无法播放。";
break;

case 1002:
r=!1,t="系统错误，请稍后再试。";
break;

case 1001:
r=!1,t="系统错误，请稍后再试。";
break;

default:
r=!1,t="系统错误，请稍后再试。";
}
return t&&(t+="错误码："+e),{
canplay:r,
msg:t
};
}
function o(e){
u.setSum(n.reportId,87,1),u.send();
var r=+new Date,t="/mp/getkugousong?params=#params#",o=[{
akey:e.akey,
albumid:e.albumid||""
}],m=encodeURIComponent(JSON.stringify(o));
t=t.replace("#params#",m),c({
url:t,
type:"GET",
dataType:"json",
success:function(t){
var o=+new Date-r;
if(setTimeout(function(){
i.reportRespData({
type:2,
songid:e.songId,
musicid:e.akey,
jumpurlkey:e.jumpurlkey,
responseData:JSON.stringify(t||{}),
kugouParams:m
});
},0),!t||"undefined"==typeof t.errcode){
var u=1;
return s({
type:"error",
time:o,
code:u
}),void("function"==typeof e.onError&&e.onError({
errcode:u
}));
}
var c=0,n="";
0==t.errcode?t.data&&t.data[0]&&t.data[0].url?(c=0,n=t.data[0].url):c=1001:c=1==t.errcode?1:1002,
s({
type:"success",
time:o,
code:c
});
var d=a(c);
e.onSuc({
canplay:d.canplay,
msg:d.msg,
errcode:c,
play_url:n
});
},
error:function(){
var t=+new Date-r,a=2;
s({
type:"error",
time:t,
code:a
}),"function"==typeof e.onError&&e.onError({
errcode:a
});
}
});
}
function s(e){
var r=Math.max(e.time,0);
if(r=Math.min(r,1e4),r>=0&&500>r?u.setSum(n.reportId,98,1):r>=500&&1e3>r?u.setSum(n.reportId,99,1):r>=1e3&&2e3>r?u.setSum(n.reportId,100,1):r>=2e3&&5e3>r?u.setSum(n.reportId,101,1):r>=5e3&&1e4>=r&&u.setSum(n.reportId,102,1),
"error"==e.type){
switch(1*e.code){
case 1:
u.setSum(n.reportId,94,1);
break;

case 2:
u.setSum(n.reportId,91,1);
break;

case 3:
u.setSum(n.reportId,92,1);
break;

case 4:
u.setSum(n.reportId,93,1);
}
u.setSum(n.reportId,88,1);
}else if("success"==e.type){
switch(1*e.code){
case 1:
u.setSum(n.reportId,95,1);
break;

case 0:
u.setSum(n.reportId,97,1);
break;

case 1002:
u.setSum(n.reportId,96,1);
break;

case 1001:
u.setSum(n.reportId,103,1);
}
u.setSum(n.reportId,89,1);
}
u.send();
}
var u=e("biz_common/utils/monitor.js"),c=e("biz_wap/utils/ajax.js"),i=e("pages/musicUrlReport.js"),n={
reportId:"28306",
musicIcon:window.icon_kugou_source||"",
cache:{},
submiting:{}
};
return{
initData:r,
getPlayUrl:t
};
});define("pages/qqmusic_ctrl.js",["biz_common/utils/monitor.js","pages/player_adaptor.js","biz_wap/jsapi/log.js","biz_wap/utils/ajax.js","pages/musicUrlReport.js"],function(e){
"use strict";
function r(e,r){
if(/^http(s)?:\/\//i.test(e.albumurl)){
for(var t,a=[/^http(s)?:\/\/imgcache\.qq\.com([\/?].*)*$/i,/^http(s)?:\/\/y\.gtimg\.cn([\/?].*)*$/i],s=!1,o=0;t=a[o++];)if(t.test(e.albumurl)){
s=!0;
break;
}
s||(e.albumurl="");
}else{
var i=e.albumurl.split("/");
try{
i=i[i.length-1],i=i.split(".")[0];
}catch(n){
i="";
}
e.albumurl=i?u.imgroot2.replace("#mid#",i):u.imgroot+e.albumurl;
}
return e.albumurl=e.albumurl.replace("mid_album_68","mid_album_90").replace("68x68","90x90"),
e.musicIcon=u.musicIcon,e.type=1*r.scene===0?0:1*r.scene===1?1:8,c.inQMClient?(e.allowPause=!0,
e.detailUrl="",e.pauseCss="qqmusic_playing_pause",e.webUrl=e.detailUrl):(e.allowPause=!1,
e.pauseCss="",e.detailUrl=["http://i.y.qq.com/v8/playsong.html?referFrom=music.qq.com&songid=",e.musicid,"&songmid=",e.media_id,,"&ADTAG=weixin_gzh#wechat_redirect"].join(""),
e.webUrl=e.detailUrl),e;
}
function t(e,r){
var t=e,a=u.cache[t.songId];
return c.inQMClient?void r.callback({
canplay:!0,
play_url:"https://www.qq.com"
}):a&&"function"==typeof r.callback&&(a.canplay||!a.canplay&&!a.retry)?(a.in_cache=!0,
void r.callback(a)):void(u.submiting[t.songId]!==!0&&(u.submiting[t.songId]=!0,a&&(i.setSum(u.reportId,122,1),
i.send()),s({
id:t.songId,
mid:t.mid,
onSuc:function(e){
u.submiting[t.songId]=!1,u.cache[t.songId]&&!u.cache[t.songId].canplay&&e.canplay&&(i.setSum(u.reportId,123,1),
i.send()),u.cache[t.songId]=e,"function"==typeof r.callback&&r.callback(e);
},
onError:function(){
u.submiting[t.songId]=!1,"function"==typeof r.callback&&r.callback({
canplay:!1,
msg:"系统繁忙，请稍后再试。",
status:-1,
play_url:"",
duration:0
});
}
})));
}
function a(e){
var r=!0,t=!1,a="";
switch(1*e){
case 0:
r=!0;
break;

case 1:
r=!1,a="因版权限制，音乐无法播放。";
break;

case 2:
r=!1,a="因版权限制，音乐无法播放。";
break;

case 3:
r=!1,a="因版权限制，音乐无法播放。";
break;

case 4:
r=!1,a="当前区域因版权限制，音乐无法播放。";
break;

case 5:
r=!1,t=!0,a="播放失败，请稍后再试。";
break;

case 6:
r=!1,t=!0,a="系统错误，请稍后再试。";
break;

case 7:
r=!1,t=!0,a="系统错误，请稍后再试。";
break;

case 8:
r=!0,a="该音乐为付费音乐，当前为你播放试听片段。";
break;

default:
r=!1,a="系统错误，请稍后再试。";
}
return{
canplay:r,
msg:a,
retry:t
};
}
function s(e){
i.setSum(u.reportId,18,1),i.send();
var r=+new Date,t="//mp.weixin.qq.com/mp/qqmusic?action=get_song_info&song_mid=#mid#";
t=t.replace("#mid#",e.mid),m({
url:t,
type:"GET",
dataType:"json",
success:function(t){
var s=+new Date-r;
if(200==t.http_code){
setTimeout(function(){
p.reportRespData({
type:1,
songid:e.id,
musicid:e.mid,
responseData:t.resp_data||""
});
},0);
var i={};
try{
i=JSON.parse(t.resp_data);
}catch(c){
var m=1;
return o({
type:"error",
time:s,
code:m
}),"function"==typeof e.onError&&e.onError({
errcode:m
}),void n.info("qqmusic_checkCopyright_parsefail mid:"+e.mid+", repsponeData:"+t.resp_data);
}
if("undefined"==typeof i.ret||0!=i.ret||0!=i.sub_ret||0==i.songlist.length){
var m=1;
return o({
type:"error",
time:s,
code:m
}),"function"==typeof e.onError&&e.onError({
errcode:m
}),void n.info("qqmusic_checkCopyright_dataerror mid:"+e.mid+", repsponeData:"+t.resp_data);
}
var u,l=i.songlist[0],d=l.song_play_url,b=l.song_play_time||0;
if(l.playable)u=d?0:6;else if(l.try_playable)l.try_file_size>0&&l.try_30s_url?(u=8,
d=l.try_30s_url,b=30):u=7;else switch(1*l.unplayable_code){
case 1:
u=1;
break;

case 2:
u=2;
break;

case 3:
u=3;
break;

case 4:
u=4;
break;

case 5:
u=5;
break;

default:
u=5;
}
o({
type:"success",
time:s,
code:u
});
var y=a(1*u);
e.onSuc({
canplay:y.canplay,
retry:y.retry,
msg:y.msg,
status:u,
play_url:d||"",
duration:b
}),y.canplay||n.info("qqmusic_checkCopyright_cannotplay mid:"+e.mid+", repsponeData:"+t.resp_data);
}else{
var m=4;
switch(t.http_code){
case 200:
break;

case 400:
m=2;
break;

case 500:
m=3;
break;

default:
m=4;
}
o({
type:"error",
time:s,
code:m
}),"function"==typeof e.onError&&e.onError({
errcode:m
});
}
},
error:function(){
"function"==typeof e.onError&&e.onError({
errcode:4
});
}
});
}
function o(e){
var r=Math.max(e.time,0);
if(r=Math.min(r,6e4),e.time>=0&&e.time<200?i.setSum(u.reportId,24,1):e.time>=200&&e.time<500?i.setSum(u.reportId,25,1):e.time>=500&&e.time<1e3?i.setSum(u.reportId,26,1):e.time>=1e3&&e.time<2e3?i.setSum(u.reportId,27,1):e.time>=2e3&&e.time<1e4?i.setSum(u.reportId,28,1):e.time>=1e4&&i.setSum(u.reportId,29,1),
i.setAvg(u.reportId,23,r),"error"==e.type){
switch(1*e.code){
case 1:
i.setSum(u.reportId,9,1);
break;

case 2:
i.setSum(u.reportId,10,1);
break;

case 3:
i.setSum(u.reportId,11,1);
break;

case 4:
i.setSum(u.reportId,12,1);
}
i.setSum(u.reportId,19,1);
}else if("success"==e.type){
switch(1*e.code){
case 1:
i.setSum(u.reportId,8,1);
break;

case 0:
i.setSum(u.reportId,17,1);
break;

case 2:
i.setSum(u.reportId,13,1);
break;

case 3:
i.setSum(u.reportId,14,1);
break;

case 4:
i.setSum(u.reportId,15,1);
break;

case 5:
i.setSum(u.reportId,16,1);
break;

case 6:
i.setSum(u.reportId,47,1);
break;

case 7:
i.setSum(u.reportId,120,1);
break;

case 8:
i.setSum(u.reportId,121,1);
}
i.setSum(u.reportId,20,1);
}
i.send();
}
var i=e("biz_common/utils/monitor.js"),c=e("pages/player_adaptor.js"),n=e("biz_wap/jsapi/log.js"),m=e("biz_wap/utils/ajax.js"),p=e("pages/musicUrlReport.js"),u={
imgroot:"https://imgcache.qq.com/music/photo/mid_album_90",
imgroot2:"https://y.gtimg.cn/music/photo_new/T002R90x90M000#mid#.jpg",
reportId:"28306",
musicIcon:window.icon_qqmusic_source||"",
cache:{},
submiting:{}
};
return{
initData:r,
getPlayUrl:t
};
});define("pages/voice_component.js",["biz_common/dom/event.js","biz_common/tmpl.js","pages/music_player.js","pages/player_adaptor.js","biz_common/dom/class.js","pages/report.js","biz_common/utils/monitor.js","pages/music_report_conf.js","pages/player_tips.js","biz_wap/jsapi/leaveReport.js","biz_wap/utils/mmversion.js","biz_wap/utils/ajax.js","biz_wap/utils/openUrl.js","pages/qqmusic_ctrl.js","pages/kugoumusic_ctrl.js"],function(e){
"use strict";
function t(){
C.hasInit||(n(),r(),s(),C.hasInit=!0);
}
function a(e){
t(),this._o={
protocal:"",
wxIndex:0,
type:0,
comment_id:"",
src:"",
jsapi2Src:"",
mid:"",
songId:"",
otherid:"",
albumid:"",
jumpurlkey:"",
autoPlay:!1,
duration:0,
needVioceMutex:!0,
appPlay:!0,
title:"",
allowPause:!1,
singer:"",
epname:"",
coverImgUrl:"",
webUrl:[location.protocol,"//mp.weixin.qq.com/s?referFrom=#referFrom#&songid=#songId#&__biz=",window.biz,"&mid=",window.mid,"&idx=",window.idx,"&sn=",window.sn,"#wechat_redirect"].join(""),
musicbar_url:"",
playingCss:"",
pauseCss:"",
playCssDom:"",
playArea:"",
progress:"",
detailUrl:"",
detailArea:"",
fileSize:0,
playtimeDom:"",
loadingDom:"",
bufferDom:"",
playdotDom:"",
seekRange:"",
seekContainer:""
},this._init(e),C.allComponent.push(this);
}
function o(e,t,a,o){
C.num++,t.musicSupport=C.musicSupport,t.show_not_support=!1,C.musicSupport||1!=C.num||(t.show_not_support=!0);
var r=document.createElement("div"),n="";
if(n=y.tmpl(e,t),r.innerHTML=n,o===!0)a.appendChild(r.children[0]);else{
var i=a.parentNode;
if(!i)return;
i.lastChild===a?i.appendChild(r.children[0]):i.insertBefore(r.children[0],a.nextSibling);
}
}
function r(){
C.hasInit||h.inQMClient&&i("QMClient_pv",1);
}
function n(){
window.reportMid=[],window.reportVoiceid=[];
for(var e in w)if(w.hasOwnProperty(e)){
var t=w[e],a=t.split("_");
C.reportData2[e]={
id:a[0],
key:a[1],
count:0
};
}
}
function i(e,t){
C.reportData2[e]&&(t=t||1,C.reportData2[e].count+=t,C.debug&&console.log("addpv:"+e+" count:"+C.reportData2[e].count));
}
function s(){
I.gtVersion("7.0.6")||g.on(window,"unload",function(){
for(var e=p(),t=JSON.parse(e.report_list),a=0;a<t.length;a++)b({
type:"POST",
url:"/mp/musicreport?#wechat_redirect",
timeout:2e4,
async:!0,
data:t[a]
});
});
}
function p(){
m.triggerUnloadPlaying(),l();
for(var e,t={},a=0,o=C.allComponent.length;o>a;a++){
var r=C.allComponent[a];
r.player&&"function"==typeof r.player.getPlayTotalTime&&(C.reportData[r._o.type].play_last_time[r._g.posIndex]=parseInt(1e3*r.player.getPlayTotalTime())),
"number"!=typeof r._status||1!==r._status&&4!==r._status||(e=r._o.songId);
}
e&&(t.current_musicid=e);
var i=[];
for(var a in C.reportData)i=i.concat(D.musicreport({
data:C.reportData[a]
}));
t.report_list=JSON.stringify(i),n();
for(var a=0,o=C.allComponent.length;o>a;a++){
var r=C.allComponent[a];
r&&"function"==typeof r._initReportData&&r._initReportData(),r.player&&"function"==typeof r.player.resetPlayTotalTime&&r.player.resetPlayTotalTime();
}
return t;
}
function l(){
for(var e in C.reportData2)if(C.reportData2.hasOwnProperty(e)){
var t=C.reportData2[e];
t.count>0&&v.setSum(t.id,t.key,t.count);
}
var a=v.getData();
a&&a.length>0&&b({
type:"POST",
url:"/mp/jsmonitor?#wechat_redirect",
timeout:2e4,
async:!1,
data:{
idkey:a.join(";"),
t:Math.random()
}
});
}
function c(e){
return new a(e);
}
function d(e){
if(isNaN(e))return"00:00";
e=Math.floor(e);
var t=Math.floor(e/3600),a=Math.floor((e-3600*t)/60),o=e-3600*t-60*a;
return 0!=t?(10>t&&(t="0"+t),t+=":"):t="",10>a&&(a="0"+a),10>o&&(o="0"+o),t+a+":"+o;
}
function u(e){
return e=(e||"").replace(/&#96;/g,"`").replace(/&#61;/g,"=").replace(/&#39;/g,"'").replace(/&quot;/g,'"').replace(/&lt;/g,"<").replace(/&gt;/g,">").replace(/&amp;/g,"&");
}
function _(e){
return e=(e||"").replace(/&/g,"&amp;").replace(/>/g,"&gt;").replace(/</g,"&lt;").replace(/"/g,"&quot;").replace(/'/g,"&#39;").replace(/=/g,"&#61;").replace(/`/g,"&#96;");
}
var g=e("biz_common/dom/event.js"),y=e("biz_common/tmpl.js"),m=e("pages/music_player.js"),h=e("pages/player_adaptor.js"),f=e("biz_common/dom/class.js"),D=e("pages/report.js"),v=e("biz_common/utils/monitor.js"),w=e("pages/music_report_conf.js"),k=e("pages/player_tips.js"),x=e("biz_wap/jsapi/leaveReport.js"),I=e("biz_wap/utils/mmversion.js"),b=e("biz_wap/utils/ajax.js"),j=e("biz_wap/utils/openUrl.js").openUrlWithExtraWebview,C={
allComponent:[],
hasInit:!1,
reportId:"28306",
musicSupport:m.getSurportType(),
debug:location.href.indexOf("vconsole=1")>0||document.cookie&&document.cookie.indexOf("vconsole_open=1")>-1?!0:!1,
reportData:{},
posIndex:{},
num:0,
reportData2:{},
adapter:{
m:e("pages/qqmusic_ctrl.js"),
k:e("pages/kugoumusic_ctrl.js")
},
needReport11982:!1
};
return a.prototype._init=function(e){
this._extend(e),this._g={
posIndex:void 0,
tag:"",
canDragBar:!1,
barDraging:!1,
canGoDetail:!0
},5==this._o.type||6==this._o.type||9==this._o.type?this._g.tag="k":this._o.type>=2&&this._o.type<=4?this._g.tag="v":7==this._o.type?this._g.tag="a":(0==this._o.type||1==this._o.type||8==this._o.type)&&(this._g.tag="m"),
this._initData(),this._initQQmusicLyric(),this._initReportData(),this._initPlayer();
},a.prototype._initData=function(){},a.prototype._initQQmusicLyric=function(){
var e=this._o,t=this._g;
e.webUrl="m"==t.tag?e.webUrl.replace("#songId#",e.songId||"").replace("#referFrom#","music.qq.com"):e.webUrl.replace("#songId#","").replace("#referFrom#","");
},a.prototype._initReportData=function(){
var e=this._o,t=this._g;
"v"==t.tag?window.reportVoiceid.push(e.songId):"m"==t.tag&&window.reportMid.push(e.songId),
"undefined"==typeof C.reportData[e.type]&&(C.reportData[e.type]=D.getMusicReportData(e),
C.posIndex[e.type]=0),"undefined"==typeof t.posIndex&&(t.posIndex=C.posIndex[e.type]++);
var a=C.reportData[e.type];
a.musicid[t.posIndex]=e.songId,a.commentid[t.posIndex]=e.comment_id,a.hasended[t.posIndex]=0,
a.mtitle[t.posIndex]=e.title,a.detail_click[t.posIndex]=0,a.duration2[t.posIndex]=parseInt(1e3*e.duration),
a.errorcode[t.posIndex]=0,a.play_duration2[t.posIndex]=0,a.seek[t.posIndex]=0,a.seek_position[t.posIndex]=[],
a.play_last_time[t.posIndex]=0,a.local_time[t.posIndex]=0,a.seek_loaded[t.posIndex]=[];
},a.prototype._initPlayer=function(){
if(C.musicSupport){
var e=this,t=this._o,a=this._g.tag;
t.onStatusChange=this._statusChangeCallBack(),t.onTimeupdate=this._timeupdateCallBack(),
t.onError=this._errorCallBack(),t.onUpdateSeekRange=this._onUpdateSeekRange(),t.onAndroidForceH5=function(){
i("force_h5",1);
},t.onH5Begin2Play=function(){
i(a+"_pv",1),i(a+"_h5_pv",1);
},t.onH5Error=function(t,o){
i(a+"_h5_err_total",1),i(a+"_h5_err_"+o.code,1),e._reportH5Error({
type:1,
code:o.code
});
},t.onJsapi1Begin2Play=function(){
i(a+"_pv",1),i(a+"_wx_pv",1),i(a+"_wx_pv_1",1);
},t.onJsapi2Begin2Play=function(e,o){
i(a+"_pv",1),i(a+"_wx_pv",1),i(a+"_wx_pv_2",1),t.jsapi2Src&&t.jsapi2Src!=t.src&&i("aac_pv",1),
t.musicPlayerOnJsapi2Begin2Play&&t.musicPlayerOnJsapi2Begin2Play(o);
},t.onJsapi2PlaySuccess=function(e,a){
t.musicPlayerOnJsapi2PlaySuccess&&t.musicPlayerOnJsapi2PlaySuccess(a);
},t.onJsapi2Begin2PlayErr=function(){
if(i(a+"_wx_err_1",1),t.jsapi2Src&&t.jsapi2Src!=t.src){
var e="acc_start_error;type:#type#;uin:"+(window.user_uin||"")+";playurl:"+t.jsapi2Src+";pageurl:"+location.href;
m.isAndroid?(D.logReport("",e.replace("#type#","android"),"ajax"),i("android_aac_err_1",1)):(D.logReport("",e.replace("#type#","ios"),"ajax"),
i("ios_aac_err_1",1));
}
},t.onJsapi2PlayingErr=function(){
if(i(a+"_wx_err_2",1),t.jsapi2Src&&t.jsapi2Src!=t.src){
var e="acc_ing_error;type:#type#;uin:"+(window.user_uin||"")+";playurl:"+t.jsapi2Src+";pageurl:"+location.href;
m.isAndroid?(D.logReport("",e.replace("#type#","android"),"ajax"),i("android_aac_err_2",1)):(D.logReport("",e.replace("#type#","ios"),"ajax"),
i("ios_aac_err_2",1));
}
},t.onJsapi2PlayingStop=function(){
var e=a+"_stoped_";
e+=m.isAndroid?"android":"ios",i(e,1);
},t.onJsapi2PlayingPause=function(){
var e=a+"_paused_";
e+=m.isAndroid?"android":"ios",i(e,1);
},t.onSeekErr=function(){
if(i(a+"_seek_err",1),t.jsapi2Src&&t.jsapi2Src!=t.src){
var e="acc_seek_error;type:#type#;uin:"+(window.user_uin||"")+";playurl:"+t.jsapi2Src+";pageurl:"+location.href;
m.isAndroid?(D.logReport("",e.replace("#type#","android"),"ajax"),i("android_aac_err_3",1)):(D.logReport("",e.replace("#type#","ios"),"ajax"),
i("ios_aac_err_3",1));
}
},t.onUnloadPlaying=function(){
i(a+"_unload_wx_pv",1);
},t.onQMClientPlay=function(){
i("QMClient_play",1);
},t.onSeekNeed2Load=function(){
if(e.player&&e.player.surportSeekRange()&&t.playdotDom){
var a=C.reportData[e._o.type],o=a.seek_position[e._g.posIndex].length;
o>0&&(a.seek_loaded[e._g.posIndex][o-1]=1);
}
},t.onSeekNotNeed2Load=function(){
if(e.player&&e.player.surportSeekRange()&&t.playdotDom){
var a=C.reportData[e._o.type],o=a.seek_position[e._g.posIndex].length;
o>0&&(a.seek_loaded[e._g.posIndex][o-1]=0);
}
},h.create(this._o,{
callback:function(t){
e.player=t,e.afterCreatePlayer();
}
});
}
},a.prototype.afterCreatePlayer=function(){
this._playEvent();
},a.prototype.isInSeekrang=function(e){
var t=this._o.seekRange;
if(!t)return!1;
if(t===e)return!0;
for(var a=t.getElementsByTagName("*"),o=0,r=a.length;r>o;o++)if(a[o]===e)return!0;
return!1;
},a.prototype._playEvent=function(){
var e=this,t=this._o,a=this._g;
if(t.detailUrl&&t.detailArea&&g.on(t.detailArea,"click",function(o){
if(!a.barDraging&&a.canGoDetail){
var r=o.target||o.srcElement;
r&&e.isInSeekrang(r)||("v"==a.tag?(C.reportData[t.type].detail_click[a.posIndex]=1,
window.__second_open__?j(t.detailUrl):window.location.href=t.detailUrl):("m"==a.tag||"k"==a.tag)&&C.adapter[a.tag].getPlayUrl(t,{
callback:function(e){
e.canplay?(C.reportData[t.type].detail_click[a.posIndex]=1,window.__second_open__?j(t.detailUrl):window.location.href=t.detailUrl):e.msg&&new k({
msg:e.msg
});
}
}));
}
}),C.musicSupport){
var o=0,r=4,n=5;
switch(1*t.type){
case 0:
o=1;
break;

case 1:
o=13;
break;

case 8:
o=14;
break;

case 2:
o=3;
break;

case 3:
o=6;
break;

case 4:
o=7;
break;

case 5:
o=10;
break;

case 6:
o=15;
break;

case 7:
o=11;
break;

case 9:
o=12;
}
var i="";
i=t.allowPause?t.pauseCss||t.playingCss:t.playingCss,g.tap(t.playArea,function(){
return console.log("click playArea",f.hasClass(t.playCssDom,i)),f.hasClass(t.playCssDom,i)?(t.allowPause?e.player.pause():e.player.stop(),
D.report({
type:o,
comment_id:t.comment_id,
voiceid:t.songId,
action:n
})):"v"==a.tag||"a"==a.tag?e._playMusic(o,r):C.adapter[a.tag].getPlayUrl(t,{
callback:function(n){
n.canplay&&n.play_url?(n.duration&&(t.duration=n.duration,e.player.setDuration(t.duration),
C.reportData[t.type].duration2[a.posIndex]=parseInt(1e3*t.duration)),e.player.setSrc(n.play_url),
8!=n.status||n.in_cache?e._playMusic(o,r):new k({
msg:"该音乐为付费音乐，当前为你播放试听片段",
onClick:function(){
e._playMusic(o,r);
}
})):n.msg&&new k({
msg:n.msg
});
}
}),!1;
}),e._dragEvent();
}
},a.prototype.getSeekRangeOffsetLeft=function(){
var e=0,t=this._o.seekRange,a=!1,o=window.__zoom||1;
for(1!=o&&(a=!0);t&&t!=document.body;)e+=a?t.offsetLeft*o:t.offsetLeft,"page-content"==t.id&&(a=!1),
t=t.offsetParent;
return e;
},a.prototype._dragEvent=function(){
var e=this,t=this._o,a=this._g,o=t.seekRange;
if(o){
var r=e.player.getDuration();
a.seekData={
zoom:window.__zoom||1,
duration:r,
startTime:0,
dragTime:0,
downX:0,
moveX:0
},g.on(o,"mousedown",function(t){
a.canDragBar&&(e._pointerDownHandler({
x:t.pageX||t.clientX
}),t.preventDefault());
}),g.on(t.seekContainer,"mousemove",function(t){
a.canDragBar&&a.barDraging&&(e._pointerMoveHandler({
x:t.pageX||t.clientX
}),t.preventDefault(),t.stopPropagation());
}),g.on(document.body,"mouseup",function(t){
return a.canDragBar&&a.barDraging?(e._pointerUpHandler({
x:t.pageX||t.clientX
}),t.preventDefault(),t.stopPropagation(),!1):void 0;
}),g.on(o,"touchstart",function(t){
a.canDragBar&&(e._pointerDownHandler({
x:t.changedTouches[0].clientX
}),t.preventDefault());
}),g.on(o,"touchmove",function(t){
a.canDragBar&&a.barDraging&&(e._pointerMoveHandler({
x:t.changedTouches[0].clientX
}),t.preventDefault(),t.stopPropagation());
}),g.on(o,"touchend",function(t){
return a.canDragBar&&a.barDraging?(e._pointerUpHandler({
x:t.changedTouches[0].clientX
}),t.preventDefault(),t.stopPropagation(),!1):void 0;
});
}
},a.prototype._pointerDownHandler=function(e){
var t=this._g;
t.barDraging=!0,t.canGoDetail=!1,t.seekData.downX=e.x,t.seekData.startTime=this.player.getCurTime();
},a.prototype._pointerMoveHandler=function(e){
var t=this._g,a=t.seekData;
a.moveX=e.x;
var o=this.getSeekRangeOffsetLeft(),r=(a.moveX-o)/a.zoom/this._o.seekRange.offsetWidth;
r=Math.min(r,1),r=Math.max(r,0),a.dragTime=r*a.duration,a.dragTime!=a.startTime&&this._updateProgressBar(a.dragTime);
},a.prototype._pointerUpHandler=function(e){
var t=this._g,a=t.seekData;
a.dragTime||this._pointerMoveHandler({
x:e.x
}),t.barDraging=!1,this.player.seek(a.dragTime),C.reportData[this._o.type].seek[t.posIndex]=1,
C.reportData[this._o.type].seek_position[t.posIndex].push(parseInt(1e3*a.startTime)+","+parseInt(1e3*a.dragTime));
var o=C.reportData[this._o.type].seek_position[t.posIndex].length;
C.reportData[this._o.type].seek_loaded[t.posIndex][o-1]=0,t.seekData.startTime=0,
t.seekData.dragTime=0,t.seekData.downX=0,t.seekData.moveX=0,setTimeout(function(){
t.canGoDetail=!0;
},1e3);
},a.prototype._playMusic=function(e,t){
var a=this._o,o=this._g;
this.player.play(),C.reportData[a.type].hasended[o.posIndex]=1,0==C.reportData[a.type].local_time[o.posIndex]&&(C.reportData[a.type].local_time[o.posIndex]=parseInt(+new Date/1e3)),
D.report({
type:e,
comment_id:a.comment_id,
voiceid:a.songId,
action:t
}),I.gtVersion("7.0.6")&&!C.needReport11982&&(C.needReport11982=!0,x.addSpecificReport("music_data",p),
console.log("music play leave report added"));
},a.prototype._extend=function(e){
for(var t in e)this._o[t]=e[t];
},a.prototype._onUpdateSeekRange=function(){
var e=this,t=e._o,a=e._g;
return function(e){
this.surportSeekRange()&&t.bufferDom&&t.playdotDom?(a.canDragBar=!0,t.playdotDom.style.display="block",
t.bufferDom.style.width=1*e+"%"):(a.canDragBar=!1,t.playdotDom&&(t.playdotDom.style.display="none"));
};
},a.prototype._statusChangeCallBack=function(){
var e=this;
return function(t,a){
e._status=a,e._updatePlayerCss(this,a),e._o.musicPlayerStatusChange&&e._o.musicPlayerStatusChange(a);
};
},a.prototype._timeupdateCallBack=function(){
var e=this,t=this._o,a=this._g;
return function(o,r){
e._updateProgress(r),0!=r&&(C.reportData[t.type].play_duration2[a.posIndex]=parseInt(1e3*r));
};
},a.prototype._errorCallBack=function(){
var e=this,t=this._o,a=this._g;
return function(o,r){
C.reportData[t.type].errorcode[a.posIndex]=r.code,e._updatePlayerCss(this,3);
};
},a.prototype._reportH5Error=function(e){
if("mp.weixin.qq.com"==location.host&&1==e.type||C.debug){
var t=["code:",e.code,";type:",this._o.type,";url:",window.location.href];
this.player&&t.push(";src:"+this.player.getSrc());
var a=new Image;
a.src=["https://badjs.weixinbridge.com/badjs?level=4&id=112&msg=",encodeURIComponent(t.join("")),"&uin=",window.uin||"","&from=",this._o.type].join("");
}
},a.prototype._updatePlayerCss=function(e,t){
!!C.debug&&console.log("status:"+t);
{
var a=this._o,o=a.playCssDom;
a.progress;
}
2==t?(f.removeClass(o,a.playingCss),a.pauseCss&&f.removeClass(o,a.pauseCss),a.playdotDom&&(e.surportSeekRange()?(a.playdotDom.style.display="block",
this._g.canDragBar=!0):(a.playdotDom.style.display="none",this._g.canDragBar=!1))):3==t?(f.removeClass(o,a.playingCss),
a.pauseCss&&f.removeClass(o,a.pauseCss),a.playdotDom&&(a.playdotDom.style.display="none",
this._g.canDragBar=!1),this._updateProgress(0)):(1==t||4==t)&&(a.allowPause?f.addClass(o,a.pauseCss||a.playingCss):f.addClass(o,a.playingCss),
a.playdotDom&&(e.surportSeekRange()?(a.playdotDom.style.display="block",this._g.canDragBar=!0):(a.playdotDom.style.display="none",
this._g.canDragBar=!1))),a.loadingDom&&(a.loadingDom.style.display=4==t?"block":"none");
},a.prototype._updateProgress=function(e){
this._g.barDraging||this._updateProgressBar(e);
},a.prototype._updateProgressBar=function(e){
var t=this._o,a=this.player,o=a.getDuration();
if(o){
var r=this._countProgress(o,e);
t.progress&&(t.progress.style.width=r),t.playtimeDom&&e>=0&&(t.playtimeDom.innerHTML=d(e)),
t.playdotDom&&(t.playdotDom.style.left=r);
}
},a.prototype._countProgress=function(e,t){
return Math.min(t/e*100,100)+"%";
},a.prototype.destory=function(){
this.player&&this.player.destory();
},a.prototype.setOption=function(e){
e.duration&&(this._g.seekData.duration=e.duration),this._extend(e);
},a.prototype.setMusicPlayerOption=function(e){
e.duration&&this._g&&this._g.seekData&&(this._g.seekData.duration=e.duration),this.player&&this.player.setOption(e);
},a.prototype.getBackgroundAudioState=function(e){
return this.player.getBackgroundAudioState(e);
},{
init:c,
renderPlayer:o,
formatTime:d,
decodeStr:u,
encodeStr:_
};
});