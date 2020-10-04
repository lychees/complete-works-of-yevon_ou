define("appmsg/weproduct.js",["appmsg/weapp_common.js","biz_common/dom/event.js","biz_wap/utils/ajax.js","biz_common/utils/url/parse.js","biz_common/utils/monitor.js","common/utils.js"],function(t){
"use strict";
function e(){
if(console.log("weproduct init"),"function"==typeof document.getElementsByClassName){
var t=document.getElementsByClassName("js_product_container");
t&&t.length>0&&(a(t),d.getAppidInfo({
onSuccess:function(e){
g.data=e.data,o(t);
}
})),r();
}
}
function a(t){
try{
for(var e=0,a=t.length;a>e;e++){
var o=t[e];
if(o.className.indexOf("js_list_container")>=0){
var i=o.querySelector("img.js_cover");
if(i){
var r=i.parentNode.getBoundingClientRect();
i.style.setProperty("width",r.width+"px","important"),i.style.setProperty("height",r.height+"px","important"),
i.style.setProperty("background-size","unset","important"),"0"==i.getAttribute("data-fail")?n.call(i):i.getAttribute("data-fail")||(i.lazyLoadOnload=i.lazyLoadOnload||[],
i.lazyLoadOnload.push(n));
}
}
}
}catch(p){}
}
function n(){
var t=this.parentNode;
if(t){
var e=document.createElement("span");
e.className=this.className,e.style.background='url("'+this.src+'") no-repeat center',
t.insertBefore(e,this),t.removeChild(this);
}
}
function o(t){
for(var e=0,a=t.length;a>e;e++)!function(t,e){
c.on(t,"tap",".js_product_loop_content",function(t){
var a=t.delegatedTarget,n=a.getAttribute("data-wxaappid"),o=a.getAttribute("data-wxapath"),i=a.getAttribute("data-pid"),r=a.getAttribute("data-appid");
return d.jumpUrl({
privateExtraData:{
cookies:"cps_package=123456; expires=1538286412; busid=mmbiz_ad_cps; domain=*"
},
sourceAppId:r,
appid:n,
path:o,
scene:1091,
sceneNote:encodeURIComponent(location.href)+":"+encodeURIComponent(i),
beforeNonWechatWarn:function(){},
beforeJumpBackupPage:function(){},
onJsapiCallback:function(t){
if("openWeApp:ok"===t.err_msg&&i){
var o=a.getAttribute("data-pidtype"),r=2;
2==o&&(r=4),p([{
wxa_appid:n,
pid:i,
type:r,
absolute_order:e+1,
appid:a.getAttribute("data-appid")||"",
templateid:a.getAttribute("data-templateid")||"",
relative_order:1*a.getAttribute("data-order"),
packid:a.getAttribute("data-packid")||""
}]);
}
}
}),!1;
});
}(t[e],e);
var n=document.getElementsByClassName("js_product_loop_content");
if(n&&n.length>0&&m.getInnerHeight()){
for(var e=0;e<n.length;e++)g.pvele.push(n[e]);
i(),c.on(window,"scroll",i);
}
}
function i(){
g.checkInScreenId&&clearTimeout(g.checkInScreenId),g.checkInScreenId=setTimeout(function(){
g.checkInScreenId=null;
for(var t=[],e=0;e<g.pvele.length;e++){
var a=g.pvele[e],n=a.getBoundingClientRect(),o=n.height||n.bottom-n.top;
if(o>0&&n.top<m.getInnerHeight()&&n.bottom>0){
var r=a.getAttribute("data-pid");
if(r){
var d=a.getAttribute("data-pidtype"),s=1;
2==d&&(s=3),t.push({
wxa_appid:a.getAttribute("data-wxaappid"),
pid:r,
type:s,
absolute_order:e+1,
appid:a.getAttribute("data-appid")||"",
templateid:a.getAttribute("data-templateid")||"",
relative_order:1*a.getAttribute("data-order"),
packid:a.getAttribute("data-packid")||""
});
}
g.pvele.splice(e--,1);
}
}
p(t),0==g.pvele.length&&(c.off(window,"scroll",i),i=null);
},100);
}
function r(){
setTimeout(function(){
var t=document.getElementsByClassName("js_product_loop_content").length,e=document.getElementsByClassName("js_product_err_container").length;
u.setSum("64469","15",t+e),u.setSum("64469","16",t),u.setSum("64469","18",e),u.send();
},0);
}
function p(t){
if(t&&0!=t.length){
for(var e={
batch_no:l.getQuery("batch_no")||"",
bizuin:window.biz||"",
biz:window.biz||"",
mid:window.mid||"",
idx:window.idx||"",
total:t.length
},a=0;a<t.length;a++){
var n=t[a],o=a+1;
for(var i in n)n.hasOwnProperty(i)&&(e[i+""+o]=n[i]);
}
s({
url:"/mp/productreport?",
type:"POST",
data:e,
dataType:"json",
async:!0
});
}
}
var d=t("appmsg/weapp_common.js"),c=t("biz_common/dom/event.js"),s=t("biz_wap/utils/ajax.js"),l=t("biz_common/utils/url/parse.js"),u=t("biz_common/utils/monitor.js"),m=t("common/utils.js"),g={
pvele:[],
checkInScreenId:null,
reportRandom:Math.random()
};
e();
});define("appmsg/voicemsg.js",["biz_wap/jsapi/core.js","biz_common/dom/event.js","biz_common/dom/class.js"],function(e){
"use strict";
function o(e){
return document.getElementById(e);
}
function i(){
"1"==window.show_msg_voice&&(s.invoke("getBackgroundAudioState",{},function(e){
console.log("voicemsg getBackgroundAudioState res",e);
var i="waiting"==e.playState||"seeked"==e.playState||"seeking"==e.playState||"play"==e.playState;
e.paused=1*e.paused,e&&!e.paused&&i&&e.src&&e.src.indexOf("/mp/msgvoice?action=get_voice")>=0?a||(o("js_msgvoice_reading").style.display="",
o("js_msgvoice_reading_title").innerHTML=e.title,console.log("hello msgvoice reading"),
n.on(o("js_msgvoice_reading"),"click",function(){
location.href=e.musicbar_url||"https://mp.weixin.qq.com/mp/msgvoice?action=ttspage&__biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&sn="+window.sn+"#wechat_redirect";
}),c.addClass(o("page-content"),"voice"),console.log("add class voice in page-content"),
a=!0):(a=!1,o("js_msgvoice_reading").style.display="none",c.removeClass(o("page-content"),"voice"),
console.log("removeClass done"));
}),console.log("begin to getBackgroundAudioState in show_msg_voice"),setTimeout(function(){
i(),4>=d&&(d++,t+=1e3);
},t)),console.log("show_msg_voice is",window.show_msg_voice);
}
var s=e("biz_wap/jsapi/core.js"),n=e("biz_common/dom/event.js"),c=e("biz_common/dom/class.js"),t=1e3,a=!1,d=0;
i();
});define("appmsg/autoread.js",["biz_common/utils/string/html.js","biz_common/dom/event.js","pages/voice_tpl.html.js","pages/voice_component.js","biz_wap/utils/ajax.js"],function(e){
"use strict";
function i(){
var e=d("autoread");
e&&(e.innerHTML='<p><label>朗读类型：</label>                                <select id="autoreadSelect">                                <option selected="true" value="0">女1</option>                                <option value="1">女2</option>                                <option value="2">男1</option>                                <option value="6">男2</option>                                </select></p><p id="autoread_voice"></p>',
r.on(d("autoreadSelect"),"change",function(){
p.player&&(p.player.destory(),p.player=null),p.checkAudioId&&(clearTimeout(p.checkAudioId),
p.checkAudioId=null);
var e=d("autoreadSelect");
d("autoread_voice").innerHTML="",o(e.value);
}),o(0));
}
function o(e){
var i=d("autoread_voice");
p._oMusic={
voiceid:p.voiceid,
duration_str:"",
posIndex:p.posIndex,
title:"文章朗读体验（"+p.voiceType[e||0]+"）",
nickname:window.nickname||"公众号"
},s.renderPlayer(u,p._oMusic,i,!0),d("voice_author_"+p.key).innerHTML="来自"+p._oMusic.nickname+"（创建音频中）",
c(e);
}
function n(e,i){
var o=p._oMusic;
d("voice_author_"+p.key).innerHTML="来自"+o.nickname,d("voice_duration_"+p.key).innerHTML=s.formatTime(1*i),
p.player=s.init({
protocal:"hls",
wxIndex:o.posIndex,
type:2,
songId:e,
src:a("https://mp.weixin.qq.com/mp/msgvoice?action=get_voice&media="+e),
allowPause:!0,
autoPlay:!0,
duration:i,
title:o.title,
singer:o.nickname?o.nickname+"的语音":"公众号语音",
epname:"来自文章",
coverImgUrl:window.__appmsgCgiData.hd_head_img,
playingCss:"share_audio_playing",
playCssDom:d("voice_main_"+p.key),
playArea:d("voice_play_"+p.key),
progress:d("voice_progress_"+p.key),
fileSize:o.fileSize,
playtimeDom:d("voice_playtime_"+p.key),
bufferDom:d("voice_buffer_"+p.key),
playdotDom:d("voice_playdot_"+p.key),
seekRange:d("voice_seekRange_"+p.key),
seekContainer:d("voice_main_"+p.key),
loadingDom:d("voice_loading_"+p.key)
});
}
function t(e){
p.curNum+=1;
var i=1e3;
p.curNum>p.maxNum&&(i=2e3);
var o=["/mp/msgvoice?action=get_media&mid=",window.mid||"","&idx=",window.idx||"","&biz=",window.biz||"","&type=",e||0].join("");
m({
url:o,
type:"GET",
dataType:"json",
async:!0,
success:function(o){
o.mediaid&&o.duration?n(o.mediaid,o.duration):p.checkAudioId=setTimeout(function(){
t(e);
},i);
},
error:function(){
p.checkAudioId=setTimeout(function(){
t(e);
},i);
}
});
}
function a(e){
return e+=["&mid=",window.mid||"","&idx=",window.idx||"","&biz=",window.biz||"","&uin=",window.uin||"","&key=",window.key||"","&pass_ticket=",window.pass_ticket||"","&clientversion=",window.clientversion||"","&devicetype=",window.devicetype||"","&wxtoken=",window.wxtoken||""].join("");
}
function c(e){
p.curNum=0;
var i=["/mp/msgvoice?action=tts&mid=",window.mid||"","&idx=",window.idx||"","&biz=",window.biz||"","&type=",e||0].join("");
m({
url:i,
type:"GET",
dataType:"json",
async:!0,
success:function(i){
i&&i.base_resp&&0==i.base_resp.ret?t(e):d("voice_author_"+p.key).innerHTML="来自"+window.nickname+"（失败）";
},
error:function(){
d("voice_author_"+p.key).innerHTML="来自"+window.nickname+"（失败）";
}
});
}
function d(e){
return document.getElementById(e);
}
e("biz_common/utils/string/html.js");
var r=e("biz_common/dom/event.js"),u=e("pages/voice_tpl.html.js"),s=e("pages/voice_component.js"),m=e("biz_wap/utils/ajax.js"),p={
checkId:"",
voiceid:"autoread",
posIndex:0,
key:"autoread_0",
voiceType:{
0:"女1",
1:"女2",
2:"男1",
6:"男2"
},
maxNum:5,
curNum:0
};
i();
});define("redpackage/redpacketcover.js",["biz_common/utils/string/html.js","redpackage/tpl/card_tpl.html.js","biz_common/dom/event.js","biz_wap/jsapi/core.js","biz_common/tmpl.js","common/utils.js","common/comm_report.js","pages/player_tips.js","biz_common/utils/url/parse.js","biz_wap/utils/mmversion.js","biz_wap/utils/ajax.js"],function(e){
"use strict";
e("biz_common/utils/string/html.js");
var t=e("redpackage/tpl/card_tpl.html.js"),a=e("biz_common/dom/event.js"),r=e("biz_wap/jsapi/core.js"),i=e("biz_common/tmpl.js"),o=e("common/utils.js"),n=e("common/comm_report.js"),d=e("pages/player_tips.js"),s=e("biz_common/utils/url/parse.js"),c=e("biz_wap/utils/mmversion.js"),u=e("biz_wap/utils/ajax.js"),p={
tagName:"redpacketcover",
isWechat:c.isWechat,
domMap:{},
dataMap:{},
startTime:window.page_begintime||0,
screen_height:o.getInnerHeight(),
screen_num:0,
pvData:[],
request_id:encodeURIComponent(window.biz+";"+window.mid+";"+window.idx+";"+window.page_begintime||0),
hasBindVisibility:!1,
hasBindScroll:!1,
needReportNum:0,
reportedNum:0
},m=function(){
var e=arguments.length<=0||void 0===arguments[0]?{}:arguments[0],t=window.pageYOffset||document.documentElement.scrollTop,a=(window.logs.read_height||t)+p.screen_height,r={
BizUin:window.biz,
MsgId:1*window.mid,
Idx:1*window.idx,
CoverUri:e.coverUri,
Scene:1*window.source,
Subscene:1*window.subscene,
CoverStatus:1*e.coverStatus,
EventType:1*e.eventType,
EventScreenNum:Math.ceil(a/p.screen_height)||1,
ScreenNum:p.screen_num,
StartTimeMs:p.startTime
};
n.report(19119,r);
},l=function(){
for(var e=window.pageYOffset||document.documentElement.scrollTop,t=e+p.screen_height,r=0;r<p.pvData.length;r++){
var i=p.pvData[r];
t>=i.start&&t<=i.end&&(p.reportedNum++,p.dataMap&&p.dataMap[i.coverUri]&&(p.dataMap[i.coverUri].reported=!0),
m({
eventType:2,
coverUri:i.coverUri,
coverStatus:p.dataMap[i.coverUri].status
}),p.pvData.splice(r,1),r--);
}
p.reportedNum>=p.needReportNum&&(a.off(window,"scroll",l),p.pvData=[],l=null);
},v=function(){
p.pvData.length>0&&(!p.hasBindScroll&&l&&(p.hasBindScroll=!0,a.on(window,"scroll",l)),
l());
},_=function(){
var e=arguments.length<=0||void 0===arguments[0]?{}:arguments[0];
if(p.isWechat){
p.scroll_height=document.body.scrollHeight||document.body.offsetHeight,p.screen_num=Math.ceil(p.scroll_height/p.screen_height);
var t=e.node;
if(p.dataMap[e.coveruri]&&1*p.dataMap[e.coveruri].status!==-1&&!p.dataMap[e.coveruri].reported){
var a=t.getBoundingClientRect();
p.pvData.push({
start:a.top+a.height/2,
end:a.top+a.height/2+p.screen_height,
coverUri:e.coveruri
});
}
v();
}
},g=null,h=function(){
var e=arguments.length<=0||void 0===arguments[0]?{}:arguments[0];
p.dataMap[e.coveruri]&&a.on(e.dom,"click",function(){
window.is_temp_url?new d({
msg:"预览时不支持领取红包封面"
}):p.isWechat?!function(){
var t=e.dom.getAttribute("data-coveruri")||"",a=t&&p.dataMap[t]?p.dataMap[t].redirect_url:"";
a&&(m({
eventType:1,
coverUri:t,
coverStatus:p.dataMap[t].status
}),r.invoke("openUrlWithExtraWebview",{
url:a,
openType:1
},function(e){
-1===e.err_msg.indexOf("ok")&&(location.href=a);
}));
}():new d({
msg:"请在微信客户端打开"
});
}),!p.hasBindVisibility&&p.isWechat&&(p.hasBindVisibility=!0,o.listenStateChange({
cb:function(e){
("onResume"===e.state_change||"onResume"===e.state)&&u({
type:"GET",
dataType:"json",
url:"/mp/wapredpacketcover?action=get_red_packet_cover_data&__biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&sn="+window.sn+"&send_time="+window.send_time,
timeout:1e4,
success:function(e){
if(e&&e.base_resp&&1*e.base_resp.ret===0&&e.red_packet_cover_data&&e.red_packet_cover_data.cover_uri_data&&e.red_packet_cover_data.cover_uri_data.length>0)for(var t=e.red_packet_cover_data.cover_uri_data,a=0,r=t.length;r>a;a++){
var i=t[a],o=p.domMap[i.cover_uri],n=p.dataMap[i.cover_uri];
if(n&&o){
var d=1*n.status,s=1*i.status;
-1!==s&&d!==s&&(n.status=s,g({
data:n,
node:o,
isUpdate:!0
}));
}
}
}
});
}
}));
};
g=function(){
var e=arguments.length<=0||void 0===arguments[0]?{}:arguments[0];
e.node&&e.data&&e.data.cover_uri&&(e.isUpdate?e.node.innerHTML=i.tmpl(t,{
data:e.data,
isUpdate:!0
}).replace(/>\s*</g,"><").replace(/^\s+/,"").replace(/\s+$/,""):e.data.receive_image&&!function(){
var a=function(e){
var a=e.node,r=e.data;
return function(){
var e=document.createElement("div");
e.innerHTML=i.tmpl(t,{
data:r,
isUpdate:!1
}).replace(/>\s*</g,"><").replace(/^\s+/,"").replace(/\s+$/,"");
var o=e.firstChild;
a.parentNode.insertBefore(o,a.nextSibling);
var n=a.parentNode.querySelector('[data-preloadingid="'+r.cover_uri+'"]');
n&&n.parentNode.removeChild(n),p.domMap[r.cover_uri]=o,h({
dom:o,
coveruri:r.cover_uri
}),_({
coveruri:r.cover_uri,
node:o
});
};
}(e),r=function(){
this.onload=null,this.onerror=null,a();
},o=new Image;
o.onload=r,o.onerror=r,o.src=e.data.receive_image;
}());
};
var w=function(){
var e=arguments.length<=0||void 0===arguments[0]?{}:arguments[0];
if(e.list&&0!==e.list.length){
for(var t=0,a=e.list.length;a>t;t++){
var r=e.list[t];
p.dataMap[r.cover_uri]=r;
}
var i=document.querySelectorAll(p.tagName);
e.list.length!==i.length&&window.__addIdKeyReport&&window.__addIdKeyReport("27613","51",1),
p.needReportNum=i.length;
for(var t=0,a=i.length;a>t;t++){
var r=i[t],o=r.getAttribute("data-coveruri")||"",n=decodeURIComponent(o),d=p.dataMap[n];
if(d&&1*d.status!==-1){
if(d.redirect_url){
var c=d.redirect_url.html(!1);
c=s.addParam(c,"request_id",p.request_id,!0);
var u=s.parseUrl(c);
u.hash?-1===u.hash.indexOf("wechat_redirect")&&(c+="&wechat_redirect"):c+="#wechat_redirect",
d.redirect_url=c;
}
g({
data:d,
node:r,
isUpdate:!1
});
}
}
}
},f=function(){
var e=document.querySelectorAll(p.tagName);
if(!window.__appmsgCgiData||1*window.__appmsgCgiData.has_red_packet_cover!==1)return void(e.length>0&&window.__addIdKeyReport&&window.__addIdKeyReport("27613","51",1));
if(!p.isWechat)for(var t=0,a=e.length;a>t;t++){
var r=e[t],i=r.getAttribute("data-coveruri")||"",o=decodeURIComponent(i),n=decodeURIComponent(r.getAttribute("data-receiveimg")||"");
if(o&&n&&/^http(s)?:\/\/mmcomm\.qpic\.cn([\/?].*)*$/i.test(n)){
var d={
cover_uri:o,
status:0,
name:"",
redirect_url:"",
receive_image:n
};
p.dataMap[o]=d,g({
data:d,
node:r,
isUpdate:!1
});
}
}
};
return f(),{
render:w
};
});define("appmsg/voice.js",["biz_common/utils/string/html.js","pages/voice_tpl.html.js","appmsg/log.js","pages/voice_component.js"],function(e){
"use strict";
function i(){
var e=a("js_content");
return e?(p._oElements=e.getElementsByTagName("mpvoice")||[],p._oElements.length<=0?!1:!0):!1;
}
function o(){
p.musicLen=p._oElements.length;
}
function n(){
for(var e=0,i=0;i<p.musicLen;i++){
var o=p._oElements[i],n={},c=o.getAttribute("voice_encode_fileid")||"";
try{
c=decodeURIComponent(c);
}catch(a){}
n.voiceid=r.encodeStr(c),n.voiceid=n.voiceid.replace(/&#61;/g,"=").replace(/^\s/,"").replace(/\s$/,""),
n.isaac=1*o.getAttribute("isaac2")||0,n.src=p.srcRoot.replace("#meidaid#",n.voiceid),
1===n.isaac&&(n.jsapi2Src=n.src+"&voice_type=1"),n.voiceid&&"undefined"!=n.voiceid&&(t(o,n,e),
e++);
}
}
function t(e,i,o){
i.duration=parseInt((1*e.getAttribute("play_length")||0)/1e3,10),i.duration_str=r.formatTime(i.duration),
i.posIndex=o;
var n=e.getAttribute("name")||"";
try{
n=decodeURIComponent(n);
}catch(t){}
i.title=r.encodeStr(n).replace(/^\s/,"").replace(/\s$/,""),i.fileSize=1*e.getAttribute("high_size")||0,
i.nickname=window.nickname,r.renderPlayer(d,i,e);
var a=i.voiceid+"_"+i.posIndex,s=e.parentNode.querySelector('[data-preloadingid="'+a+'"]');
s&&s.parentNode.removeChild(s),c(i),p.musicList[i.voiceid+"_"+i.posIndex]=i;
}
function c(e){
var i=e.voiceid+"_"+e.posIndex,o="";
if(window.voice_in_appmsg&&window.voice_in_appmsg[e.voiceid]){
var n=window.voice_in_appmsg[e.voiceid],t=window.biz||"",c=window.mid||"",d=window.idx||"";
n.bizuin&&n.appmsgid&&n.idx&&(t=n.bizuin,c=n.appmsgid,d=n.idx);
var p=window.location.protocol||"https:";
o=p+"//mp.weixin.qq.com/mp/audio?_wxindex_=#_wxindex_#&scene=104&__biz=#biz#&mid=#mid#&idx=#idx#&voice_id=#voice_id#&sn=#sn##wechat_redirect".replace("#_wxindex_#",e.posIndex).replace("#biz#",t).replace("#mid#",c).replace("#idx#",d).replace("#voice_id#",e.voiceid).replace("#sn#",n.sn||"");
}
s("[Voice] init"+o);
var m=r.decodeStr(e.title);
e.player=r.init({
wxIndex:e.posIndex,
type:2,
songId:e.voiceid,
comment_id:"",
src:e.src,
jsapi2Src:e.jsapi2Src,
allowPause:!0,
duration:e.duration,
title:m,
singer:window.nickname?window.nickname+"的语音":"公众号语音",
epname:"来自文章",
coverImgUrl:window.__appmsgCgiData.hd_head_img,
playingCss:"share_audio_playing",
playCssDom:a("voice_main_"+i),
playArea:a("voice_play_"+i),
progress:a("voice_progress_"+i),
fileSize:e.fileSize,
playtimeDom:a("voice_playtime_"+i),
bufferDom:a("voice_buffer_"+i),
playdotDom:a("voice_playdot_"+i),
seekRange:a("voice_seekRange_"+i),
seekContainer:a("voice_main_"+i),
loadingDom:a("voice_loading_"+i),
detailArea:o?a("voice_main_"+i):"",
detailUrl:o,
webUrl:o
});
}
function a(e){
return document.getElementById(e);
}
e("biz_common/utils/string/html.js");
var d=e("pages/voice_tpl.html.js"),s=e("appmsg/log.js"),r=e("pages/voice_component.js"),p={
musicList:{},
musicLen:0,
srcRoot:location.protocol+"//res.wx.qq.com/voice/getvoice?mediaid=#meidaid#"
};
return i()?(o(),n(),p.musicList):void 0;
});define("appmsg/qqmusic.js",["biz_common/utils/string/html.js","biz_common/utils/url/parse.js","appmsg/log.js","pages/qqmusic_tpl.html.js","pages/voice_component.js","pages/qqmusic_ctrl.js","pages/kugoumusic_ctrl.js"],function(e){
"use strict";
function t(){
var e=u("js_content");
return e?(p._oElements=e.getElementsByTagName("qqmusic")||[],p._oElements.length<=0?!1:!0):!1;
}
function i(){
p.musicLen=p._oElements.length;
}
function s(){
for(var e=0,t=0;t<p.musicLen;t++){
var i=p._oElements[t],s={};
s.musicid=l.encodeStr(i.getAttribute("musicid")||"").replace(/^\s/,"").replace(/\s$/,""),
s.musicid&&"undefined"!=s.musicid&&(r(i,s,e),e++);
}
}
function r(e,t,i){
if(t.media_id=l.encodeStr(e.getAttribute("mid")||"").replace(/^\s/,"").replace(/\s$/,""),
t.musictype=parseInt(e.getAttribute("musictype"))||1,t.musictype>2&&(t.musictype=2),
t.albumid=l.encodeStr(e.getAttribute("albumid")||"").replace(/^\s/,"").replace(/\s$/,""),
t.otherid=l.encodeStr(e.getAttribute("otherid")||"").replace(/^\s/,"").replace(/\s$/,""),
t.jumpurlkey=l.encodeStr(e.getAttribute("jumpurlkey")||"").replace(/^\s/,"").replace(/\s$/,""),
t.duration=parseInt(e.getAttribute("play_length")||0,10),t.posIndex=i,t.albumurl=l.encodeStr(e.getAttribute("albumurl")||"").replace(/^\s/,"").replace(/\s$/,""),
t.audiourl=l.encodeStr(e.getAttribute("audiourl")||"").replace(/^\s/,"").replace(/\s$/,""),
t.singer=l.encodeStr(e.getAttribute("singer")||"").replace(/^\s/,"").replace(/\s$/,""),
!t.singer||"undefined"==t.singer){
var s=e.getAttribute("src")||"",r=decodeURIComponent(a.getQuery("singer",s)||"");
t.singer=l.encodeStr(r).replace(/^\s/,"").replace(/\s$/,""),t.singer&&"undefined"!=t.singer||(t.singer="");
}
t.music_name=l.encodeStr(e.getAttribute("music_name")||"").replace(/^\s/,"").replace(/\s$/,""),
p.adapter[t.musictype]&&"function"==typeof p.adapter[t.musictype].initData&&(t=p.adapter[t.musictype].initData(t,{
scene:0
})),l.renderPlayer(m,t,e);
var u=t.musicid+"_"+t.posIndex,c=e.parentNode.querySelector('[data-preloadingid="'+u+'"]');
c&&c.parentNode.removeChild(c),n(t),p.musicList[t.musicid+"_"+t.posIndex]=t;
}
function n(e){
var t=e.musicid+"_"+e.posIndex;
c("[Music] init "+e.detailUrl);
var i=l.decodeStr(e.music_name);
e.player=l.init({
allowPause:e.allowPause===!0?!0:!1,
wxIndex:e.posIndex,
type:e.type||0,
comment_id:"",
mid:e.media_id,
otherid:e.otherid,
albumid:e.albumid,
songId:e.musicid,
jumpurlkey:e.jumpurlkey,
duration:e.duration,
title:i,
singer:window.nickname?window.nickname+"推荐的歌":"公众号推荐的歌",
epname:"音乐",
coverImgUrl:e.albumurl,
playingCss:"qqmusic_playing",
pauseCss:e.pauseCss||"",
playCssDom:u("qqmusic_main_"+t),
playArea:u("qqmusic_play_"+t),
detailUrl:e.detailUrl||"",
webUrl:e.webUrl||"",
detailArea:u("qqmusic_home_"+t)
});
}
function u(e){
return document.getElementById(e);
}
e("biz_common/utils/string/html.js");
var a=e("biz_common/utils/url/parse.js"),c=e("appmsg/log.js"),m=e("pages/qqmusic_tpl.html.js"),l=e("pages/voice_component.js"),p={
adapter:{
1:e("pages/qqmusic_ctrl.js"),
2:e("pages/kugoumusic_ctrl.js")
},
musicList:{},
musicLen:0
};
return t()?(i(),s(),p.musicList):void 0;
});define("appmsg/iframe.js",["biz_common/utils/string/html.js","pages/video_communicate_adaptor.js","biz_wap/utils/mmversion.js","biz_wap/utils/ajax.js","common/utils.js","appmsg/finance_communicate.js","biz_common/utils/url/parse.js","new_video/ctl.js","pages/version4video.js","biz_common/dom/attr.js","biz_common/dom/event.js"],function(e){
"use strict";
function t(e){
console.info("iframe_onload");
var t=0;
try{
e.contentDocument&&e.contentDocument.body.offsetHeight?t=e.contentDocument.body.offsetHeight:e.Document&&e.Document.body&&e.Document.body.scrollHeight?t=e.Document.body.scrollHeight:e.document&&e.document.body&&e.document.body.scrollHeight&&(t=e.document.body.scrollHeight);
var i=e.parentElement;
if(i&&(e.style.height=t+"px"),/MSIE\s(7|8)/.test(navigator.userAgent)&&e.contentWindow&&e.contentWindow.document){
var o=e.contentWindow.document.getElementsByTagName("html");
o&&o.length&&(o[0].style.overflow="hidden");
}
s&&s.postPageHeightMessage&&s.postPageHeightMessage("updatePageHeight"),console.log("financeUtils done");
}catch(n){}
}
function i(){
for(var e=window.pageYOffset||document.documentElement.scrollTop,t=m.video_top.length,n=e+r.getInnerHeight(),d=0,s=0;t>s;s++){
var c=m.video_top[s];
c.reported?d++:n>=c.start&&n<=c.end&&(c.reported=!0,setTimeout(function(e,t,i){
return function(){
var n=o.getVideoInfo(),d="",r="",s=3;
n[e]&&(n[e].hit_bizuin&&(d=n[e].hit_bizuin),n[e].hit_vid&&(r=n[e].hit_vid),n[e].ori_status&&(s=n[e].ori_status)),
a.report({
step:1,
hit_vid:r,
hit_bizuin:d,
ori_status:s,
vid:e,
screen_num:Math.ceil(t/i),
screen_height:i
});
};
}(c.vid,n,r.getInnerHeight()),1e4));
}
d==t&&(l.off(window,"scroll",i),m.video_top=m.video_iframe=i=null);
}
e("biz_common/utils/string/html.js");
{
var o=e("pages/video_communicate_adaptor.js"),n=e("biz_wap/utils/mmversion.js"),d=e("biz_wap/utils/ajax.js"),r=e("common/utils.js"),s=e("appmsg/finance_communicate.js"),c=e("biz_common/utils/url/parse.js"),a=e("new_video/ctl.js"),m={
txVideoReg:/^http(s)*\:\/\/v\.qq\.com\/iframe\/(preview|player)\.html\?/,
mpVideoReg:/^http(s)*\:\/\/mp\.weixin\.qq\.com\/mp\/readtemplate\?t=pages\/video_player_tmpl/,
video_iframe:[],
video_top:[]
},p=e("pages/version4video.js"),_=e("biz_common/dom/attr.js"),l=(_.setProperty,e("biz_common/dom/event.js")),u=document.getElementsByTagName("iframe"),w=[];
/MicroMessenger/.test(navigator.userAgent);
}
window.reportVid=[];
for(var f=Math.ceil(1e4*Math.random()),g=0,v=u.length;v>g;++g)!function(e){
var i=e.getAttribute("data-src")||"",o=e.className||"",r=e.getAttribute("src")||i;
if(!i||"#"==i){
var s=e.getAttribute("data-display-src");
if(s&&(0==s.indexOf("/cgi-bin/readtemplate?t=vote/vote-new_tmpl")||0==s.indexOf("https://mp.weixin.qq.com/cgi-bin/readtemplate?t=vote/vote-new_tmpl"))){
s=s.replace(/&amp;/g,"&");
for(var a=s.split("&"),_=["/mp/newappmsgvote?action=show"],l=0;l<a.length;l++)(0==a[l].indexOf("__biz=")||0==a[l].indexOf("supervoteid="))&&_.push(a[l]);
_.length>1&&(i=_.join("&")+"#wechat_redirect");
}
}
if(r&&(m.txVideoReg.test(r)||m.mpVideoReg.test(r))){
if(p.isShowMpVideo()||m.mpVideoReg.test(r)){
var u=c.getQuery("vid",i);
if(!u)return;
var g=e.getAttribute("data-vw"),v=e.getAttribute("data-vh"),h=document.domain;
"qq.com"==h&&((new Image).src="https://badjs.weixinbridge.com/badjs?id=139&level=4&from="+window.encodeURIComponent(window.location.host)+"&msg="+window.encodeURIComponent(window.location.href),
(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=27302_100_1&lc=1&log0=[beforeD]"+window.encodeURIComponent(window.location.href)),
window.reportVid.push(u),m.video_iframe.push({
dom:e,
vid:u
}),r=["/mp/videoplayer?video_h=",v,"&video_w=",g,"&scene=",window.source,"&random_num=",f,"&article_title=",encodeURIComponent(window.msg_title.htmlDecode()),"&source=4&vid=",u,"&mid=",appmsgid,"&idx=",itemidx||idx,"&__biz=",biz,"&nodetailbar=",window.is_temp_url?1:0,"&uin=",uin,"&key=",key,"&pass_ticket=",pass_ticket,"&version=",version,"&devicetype=",window.devicetype||"","&wxtoken=",window.wxtoken||"","&sessionid=",window.sessionid||"","&preview=",window.is_temp_url?1:0].join(""),
uin||window.__addIdKeyReport&&window.__addIdKeyReport("28307",21),window.__addIdKeyReport&&window.__addIdKeyReport("28307",11),
setTimeout(function(e,t){
if(t.setAttribute("marginWidth",0),t.setAttribute("marginHeight",0),t.style.top="0",
window.__second_open__)if(n.isIOS){
var i,o,r;
!function(){
var n=function(e,t,i,o){
i&&o&&(e.contentWindow.is_login=t.is_login,e.contentWindow.user_uin=t.user_uin,e.contentWindow.cgiData.ckey=t.ckey,
e.contentWindow.cgiData.ckey_ad=t.ckey_ad,e.contentWindow.seajs.use("pages/video_appmsg.js"));
};
window.__videohook__=1,i=!1,o=!1,r={},t.onload=function(){
console.log("4",Date.now()),i=!0,n(t,r,i,o);
},t.setAttribute("src",e),d({
url:e,
type:"GET",
f:"json",
success:function(d){
o=!0;
try{
r=JSON.parse(d),n(t,r,i,o);
}catch(s){
n(t,r,i,o);
}
window.resp=d,t.setAttribute("data-realsrc",e),t.contentWindow.__iframe_src__=e;
}
});
}();
}else d({
url:e,
type:"GET",
f:"html",
success:function(i){
t.setAttribute("data-realsrc",e),t.contentDocument.open("text/html","replace"),t.contentDocument.write(i),
t.contentDocument.close(),t.contentWindow.__iframe_src__=e,t.contentWindow.history.replaceState(null,null,e);
}
});else t.setAttribute("src",e);
},0,r,e);
}
}else if(i&&(i.indexOf("newappmsgvote")>-1&&(o.indexOf("js_editor_vote_card")>=0||o.indexOf("vote_iframe")>=0)||0==i.indexOf("http://mp.weixin.qq.com/bizmall/appmsgcard")&&(o.indexOf("card_iframe")>=0||o.indexOf("js_editor_card")>=0)||i.indexOf("appmsgvote")>-1||i.indexOf("mp.weixin.qq.com/mp/getcdnvideourl")>-1)){
if(window.is_transfer_msg&&!window.reprint_ticket&&i.indexOf(window.biz)<0)return void w.push(e);
if(window.__second_open__||(i=i.replace(/^http:/,location.protocol)),o.indexOf("card_iframe")>=0||o.indexOf("js_editor_card")>=0){
-1===o.indexOf("card_iframe")&&(e.className+=" card_iframe"),-1===o.indexOf("res_iframe")&&(e.className+=" res_iframe");
var x=i.replace("#wechat_redirect",["&pass_ticket=",pass_ticket,"&scene=",source,"&msgid=",appmsgid,"&msgidx=",itemidx||idx,"&version=",version,"&devicetype=",window.devicetype||"","&child_biz=",biz,"&wxtoken=",window.wxtoken||""].join(""));
reprint_ticket&&(x+=["&mid=",mid,"&idx=",idx,"&reprint_ticket=",reprint_ticket,"&source_mid=",source_mid,"&source_idx=",source_idx].join("")),
window.__second_open__?d({
url:x,
type:"GET",
f:"html",
success:function(o){
e.setAttribute("src",x),e.contentWindow.document.open("text/html","replace"),e.contentWindow.document.write(o),
e.contentWindow.document.close(),e.contentWindow.history.replaceState(null,null,x),
-1==i.indexOf("mp.weixin.qq.com/mp/getcdnvideourl")&&(e.onload=function(){
t(e);
});
}
}):(e.setAttribute("src",x),-1==i.indexOf("mp.weixin.qq.com/mp/getcdnvideourl")&&(e.onload=function(){
t(e);
}));
}else{
var y=i.indexOf("#wechat_redirect")>-1,b=["&uin=",uin,"&key=",key,"&pass_ticket=",pass_ticket,"&wxtoken=",window.wxtoken||""].join("");
reprint_ticket?b+=["&mid=",mid,"&idx=",idx,"&reprint_ticket=",reprint_ticket,"&source_mid=",source_mid,"&source_idx=",source_idx,"&appmsg_token=",appmsg_token].join(""):(o.indexOf("vote_iframe")>=0||o.indexOf("js_editor_vote_card")>=0)&&(b+=["&mid=",mid,"&idx=",idx,"&appmsg_token=",appmsg_token].join(""),
-1===o.indexOf("vote_iframe")&&(e.className+=" vote_iframe"));
var x=y?i.replace("#wechat_redirect",b):i+b;
window.__second_open__?d({
url:x,
type:"GET",
f:"html",
success:function(o){
e.contentWindow.Ajax=d,e.setAttribute("src",x),e.contentWindow.document.open("text/html","replace"),
e.contentWindow.document.write(o),e.contentWindow.document.close(),e.contentWindow.history.replaceState(null,null,x),
-1==i.indexOf("mp.weixin.qq.com/mp/getcdnvideourl")&&(e.onload=function(){
t(e);
});
}
}):(e.setAttribute("src",x),-1==i.indexOf("mp.weixin.qq.com/mp/getcdnvideourl")&&(e.onload=function(){
t(e);
}));
}
e.appmsg_idx=l;
}
if(i&&i.indexOf("mp.weixin.qq.com/mp/getcdnvideourl")>-1&&g>0){
var j=g,k=3*j/4;
e.width=j,e.height=k,e.style.setProperty&&(e.style.setProperty("width",j+"px","important"),
e.style.setProperty("height",k+"px","important"));
}
}(u[g]);
for(var h=0;h<w.length;h++){
var x=w[h];
x.parentNode.removeChild(x);
}
if(window.iframe_reload=function(){
for(var e=0,i=u.length;i>e;++e){
var o=u[e],n=o.getAttribute("src");
n&&(n.indexOf("newappmsgvote")>-1||n.indexOf("appmsgvote")>-1)&&t(o);
}
},"getElementsByClassName"in document)for(var y,b=document.getElementsByClassName("video_iframe"),g=0;y=b.item(g++);)y.setAttribute("scrolling","no"),
y.style.overflow="hidden";
m.video_iframe.length>0&&setTimeout(function(){
for(var e=m.video_iframe,t=document.getElementById("js_article"),o=0,n=e.length;n>o;o++){
var d=e[o];
if(!d||!d.dom)return;
for(var s=d.dom,c=s.offsetHeight,a=0;s&&t!==s;)a+=s.offsetTop,s=s.offsetParent;
m.video_top.push({
start:a+c/2,
end:a+c/2+r.getInnerHeight(),
reported:!1,
vid:d.vid
});
}
i(),l.on(window,"scroll",i);
});
});define("appmsg/page_pos.js",["biz_common/utils/string/html.js","biz_common/dom/event.js","biz_wap/utils/ajax.js","biz_common/utils/cookie.js","biz_common/utils/http.js","appmsg/cdn_img_lib.js","biz_wap/utils/storage.js","biz_wap/utils/hand_up_state.js","biz_wap/utils/mmversion.js","biz_wap/jsapi/core.js","biz_wap/jsapi/leaveReport.js","biz_wap/utils/wapsdk.js","common/utils.js","appmsg/log.js","biz_common/utils/url/parse.js"],function(e){
"use strict";
function t(e){
window.logs||(window.logs={}),j.js_content=e.js_content||document.getElementById("js_content");
var t=e.js_toobar3||document.getElementById("js_toobar3");
j.pageEndTop=t?t.offsetTop:0,j.imgs=j.js_content?j.js_content.getElementsByTagName("img")||[]:[],
j.media=e.media||document.getElementById("media"),j.title=e.title||(window.msg_title||"").htmlDecode(),
j.video_cnt=e.video_cnt||window.logs.video_cnt||0,j.js_cmt_area=e.js_cmt_area||document.getElementById("js_cmt_area"),
j.item_show_type=e.item_show_type||window.item_show_type||0,l=document.getElementsByTagName("html"),
l&&1==!!l.length&&c&&(l=l[0].innerHTML,I.content_length=c.htmlSize),window.logs.pageinfo=I,
function(){
if(window.localStorage&&!localStorage.getItem("clear_page_pos")){
for(var e=localStorage.length-1;e>=0;){
var t=localStorage.key(e);
t.match(/^\d+$/)?localStorage.removeItem(t):t.match(/^adinfo_/)&&localStorage.removeItem(t),
e--;
}
localStorage.setItem("clear_page_pos","true");
}
}(),window.localStorage&&(w.on(window,"load",function(){
if(B=1*T.get(N),!window.__second_open__){
var t=location.href.indexOf("scrolltodown")>-1,o=j.js_cmt_area;
if(t&&o&&o.offsetTop){
var i=o.offsetTop;
!e.disableScroll&&window.scrollTo(0,i-25);
}else!e.disableScroll&&window.scrollTo(0,B),b.saveSpeeds({
uin:uin,
pid:"https:"==O?462:417,
speeds:{
sid:36,
time:Math.ceil(B/v.getInnerHeight())
}
}),b.send();
}
if(window.__wxjs_is_wkwebview||window.__second_open__){
if(M)return;
var n=z.getData(),m=localStorage.getItem("hand_up_id");
for(var w in n)w!=m&&n[w]&&(s(n[w].val),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_59_1&r="+Math.random(),
z.remove(w));
window.setInterval(function(){
var e=a();
z.set(P,e,+new Date+864e7);
},1e3);
}
var c=S.getData("spad");
c&&c.spad&&_(c.spad.val),e.hasSpAd&&window.setInterval(function(){
d();
var e=r();
S.set("spad",e,+new Date+864e7);
},1e3),window.setTimeout(function(){
p({
url:"/mp/appmsgreport?action=page_time_5s&__biz="+biz,
type:"POST",
mayAbort:!0,
data:a(),
async:!0,
timeout:2e3
});
},5e3);
}),w.on(window,"unload",function(){
if(!window.__second_open__&&!window.__jsapi_report_has_done__){
localStorage.setItem("hand_up_id",""),window.__ajaxtest="2";
var e=a();
s(e),window.__unload_has_done__=!0;
}
}),window.logs.read_height=0,w.on(window,"scroll",function(){
var e=window.pageYOffset||document.documentElement.scrollTop;
window.logs.read_height=Math.max(window.logs.read_height,e),clearTimeout(D),D=setTimeout(function(){
B=window.pageYOffset,T.set(N,B,+new Date+72e5);
},500);
}),w.on(document,"touchmove",function(){
var e=window.pageYOffset||document.documentElement.scrollTop;
window.logs.read_height=Math.max(window.logs.read_height,e),clearTimeout(D),D=setTimeout(function(){
B=window.pageYOffset,T.set(N,B,+new Date+72e5);
},500);
})),f.addReport(function(){
if(!window.__unload_has_done__){
k=!0,z.remove(P);
var e=a(),t=[];
for(var o in e)e.hasOwnProperty(o)&&t.push(o+"="+encodeURIComponent(e[o]));
var i={
reportUrl:"https://mp.weixin.qq.com/mp/appmsgreport?action=page_time&__biz="+biz,
reportData:t.join("&"),
method:"POST"
};
return window.__jsapi_report_has_done__=!0,y("[Appmsg leaveReport length]: "+JSON.stringify(i).length),
i;
}
}),w.on(document,"visibilitychange",function(){
u.isHidden()?localStorage.setItem("hand_up_id",P):localStorage.setItem("hand_up_id","");
}),m();
}
function o(e,t){
if(e&&!(e.length<=0))for(var o,i,n,a=/http(s)?\:\/\/([^\/\?]*)(\?|\/)?/,s=0,d=e.length;d>s;++s)o=e[s],
o&&(i=o.getAttribute(t),i&&(n=i.match(a),n&&n[2]&&(x[n[2]]=!0)));
}
function i(e){
for(var t=0,o=A.length;o>t;++t)if(A[t]==e)return!0;
return!1;
}
function n(){
x={},o(document.getElementsByTagName("a"),"href"),o(document.getElementsByTagName("link"),"href"),
o(document.getElementsByTagName("iframe"),"src"),o(document.getElementsByTagName("script"),"src"),
o(document.getElementsByTagName("img"),"src");
var e=[];
for(var t in x)x.hasOwnProperty(t)&&(window.networkType&&"wifi"==window.networkType&&!E&&i(t)&&(E=!0),
e.push(t));
return x={},e.join(",");
}
function a(){
{
var e,t=window.pageYOffset||document.documentElement.scrollTop,o=j.js_content,i=v.getInnerHeight(),a=j.screen_width,s=j.scroll_height,d=Math.ceil(s/i),r=Math.ceil((o.scrollHeight||o.offsetHeight)/i),_=(window.logs.read_height||t)+i,m=j.pageEndTop,w=j.imgs,p=Math.ceil(_/i)||1,c=j.media,g=50,h=0,f=0,b=0,y=0,T=_+g>m?1:0;
o.offsetTop+o.scrollHeight;
}
p>d&&(p=d);
var z=function(t){
if(t)for(var o=0,i=t.length;i>o;++o){
var n=t[o];
if(n){
h++;
var a=n.getAttribute("src"),s=n.getAttribute("data-type");
a&&0==a.indexOf("http")&&(f++,a.isCDN()&&(b++,-1!=a.indexOf("tp=webp")&&y++),s&&(e["img_"+s+"_cnt"]=e["img_"+s+"_cnt"]||0,
e["img_"+s+"_cnt"]++));
}
}
e.download_cdn_webp_img_cnt=y||0,e.download_img_cnt=f||0,e.download_cdn_img_cnt=b||0,
e.img_cnt=h||0;
},S=window.appmsgstat||{},x=window.logs.img||{},O=window.logs.pagetime||{},A=x.load||{},k=x.read||{},D=[],B=[],N=0,H=0,P=0;
for(var M in k)M&&0==M.indexOf("http")&&k.hasOwnProperty(M)&&B.push(M);
for(var M in A)M&&0==M.indexOf("http")&&A.hasOwnProperty(M)&&D.push(M);
for(var q=0,R=D.length;R>q;++q){
var G=D[q];
G&&G.isCDN()&&(-1!=G.indexOf("/0")&&N++,-1!=G.indexOf("/640")&&H++,-1!=G.indexOf("/300")&&P++);
}
var e={
report_bizuin:biz,
title:j.title,
mid:mid,
idx:idx,
subscene:window.subscene||1e4,
sessionid:window.sessionid||0,
read_cnt:S.read_num||0,
like_cnt:S.like_num||0,
screen_width:a,
screen_height:v.getInnerHeight(),
screen_num:r,
idkey:"",
copyright_stat:"",
ori_article_type:"",
video_cnt:j.video_cnt,
read_screen_num:p||0,
is_finished_read:T,
scene:source,
content_len:I.content_length||0,
start_time:page_begintime,
end_time:(new Date).getTime(),
handup_time:u.getHandUpTime(),
total_height:m,
exit_height:_>m?m:_,
img_640_cnt:H,
img_0_cnt:N,
img_300_cnt:P,
wtime:O.onload_time||0,
ftime:O.ftime||0,
ptime:O.ptime||0,
onload_time:O.onload_time||0,
reward_heads_total:window.logs.reward_heads_total||0,
reward_heads_fail:window.logs.reward_heads_fail||0,
outer_pic:window.logs.outer_pic||0,
publish_time:window.ct,
item_show_type:j.item_show_type,
page_req_info:JSON.stringify({
startGetAppmsgExtTime:window.startGetAppmsgExtTime,
startGetAppmsgAdTime:window.startGetAppmsgAdTime,
receiveGetAppmsgExt:window.receiveGetAppmsgExt,
receiveGetAppmsgAd:window.receiveGetAppmsgAd,
jsapiReadyTime:window.jsapiReadyTime,
domCompleteTime:window.domCompleteTime
})
};
if(window.networkType&&"wifi"==window.networkType&&(e.wifi_all_imgs_cnt=D.length,
e.wifi_read_imgs_cnt=B.length),window.logs.webplog&&4==window.logs.webplog.total){
var C=window.logs.webplog;
e.webp_total=1,e.webp_lossy=C.lossy,e.webp_lossless=C.lossless,e.webp_alpha=C.alpha,
e.webp_animation=C.animation;
}
if(e.copyright_stat=window._copyright_stat||"",e.ori_article_type=window._ori_article_type||"",
window.__addIdKeyReport&&window.moon&&(moon.hit_num>0&&moon.hit_num<1e3&&window.__addIdKeyReport(27613,30,moon.hit_num),
moon.mod_num>0&&moon.mod_num<1e3&&window.__addIdKeyReport(27613,31,moon.mod_num)),
window.logs.idkeys){
var Y=window.logs.idkeys,J=[];
for(var K in Y)if(Y.hasOwnProperty(K)){
var U=Y[K];
U.val>0&&J.push(K+"_"+U.val);
}
e.idkey=J.join(";");
}
z(!!c&&c.getElementsByTagName("img")),z(w);
var L=(new Date).getDay(),V=n();
return(E||0!==user_uin&&Math.floor(user_uin/100)%7==L)&&(e.domain_list=V),E&&(e.html_content=l),
window.isSg&&(e.from="sougou"),e.source=window.friend_read_source||"",e.req_id=window.req_id||"",
e.recommend_version=window.friend_read_version||"",e.class_id=window.friend_read_class_id||"",
e.ascene=window.ascene||-1,0==e.scene&&56==e.ascene&&(e.scene=90),e.hotspotjson=JSON.stringify({
hotspotinfolist:window.hotspotInfoList||[]
}),e.is_pay_subscribe=window.isPaySubscribe,e.is_paid=window.isPaid,e.preview_percent=window.previewPercent,
e.is_finished_preview=window.is_finished_preview||0,e.fee=window.paySubscribeInfo?window.paySubscribeInfo.fee:"",
e.pay_cnt=window.paySubscribeInfo?window.paySubscribeInfo.pay_cnt:"",e.worthy_cnt=window.paySubscribeInfo?window.paySubscribeInfo.like_cnt:"",
e;
}
function s(e){
k||(k=!0,z.remove(P),e.report_time=parseInt(+new Date/1e3),p({
url:"/mp/appmsgreport?action=page_time&__biz="+biz,
type:"POST",
mayAbort:!0,
data:e,
async:!1,
timeout:2e3
}));
}
function d(){
T.set(N,B,+new Date+72e5);
}
function r(){
return window.__video_report_data;
}
function _(e){
e&&e.play_type&&(S.remove("spad"),e.report_type=1,p({
url:"/mp/ad_video_report?action=video_play_report",
type:"POST",
mayAbort:!0,
data:e,
async:!1,
timeout:2e3
}));
}
function m(){
(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/geticon?__biz="+biz+"&r="+Math.random();
}
e("biz_common/utils/string/html.js");
var w=e("biz_common/dom/event.js"),p=e("biz_wap/utils/ajax.js"),c=(e("biz_common/utils/cookie.js"),
e("biz_common/utils/http.js"));
e("appmsg/cdn_img_lib.js");
var l,g=e("biz_wap/utils/storage.js"),u=e("biz_wap/utils/hand_up_state.js"),h=e("biz_wap/utils/mmversion.js"),f=(e("biz_wap/jsapi/core.js"),
e("biz_wap/jsapi/leaveReport.js")),b=e("biz_wap/utils/wapsdk.js"),v=e("common/utils.js"),y=e("appmsg/log.js"),j=(e("biz_common/utils/url/parse.js"),
-1!=navigator.userAgent.indexOf("TBS/"),{
js_cmt_area:null,
js_content:null,
screen_height:v.getInnerHeight(),
screen_width:document.documentElement.clientWidth||window.innerWidth,
scroll_height:document.body.scrollHeight||document.body.offsetHeight,
pageEndTop:0,
imgs:[],
media:null,
title:"",
video_cnt:0,
item_show_type:0
}),T=new g("page_pos"),z=new g("time_on_page"),S=new g("spad"),I={},x={},O=window.location.protocol,E=!1,A=["wap.zjtoolbar.10086.cn","125.88.113.247","115.239.136.61","134.224.117.240","hm.baidu.com","c.cnzz.com","w.cnzz.com","124.232.136.164","img.100msh.net","10.233.12.76","wifi.witown.com","211.137.132.89","qiao.baidu.com","baike.baidu.com"],k=!1,D=null,B=0,N=[biz,sn,mid,idx].join("_"),H=Math.random(),P=[biz,sn,mid,idx,H].join("_"),M=h.isAndroid&&h.gtVersion("7.0.4",!0)||h.isIOS&&h.gtVersion("7.0.4",!0);
return{
init:t
};
});define("appmsg/product.js",["biz_common/dom/event.js","common/utils.js"],function(e){
"use strict";
function t(){
for(var e=window.pageYOffset||document.documentElement.scrollTop,t=0;t<i.length;++t){
var o=i[t];
if(!o.isReport){
var n=o.offsetTop;
n>=e&&e+r.getInnerHeight()>=n&&(o.isReport=!0,(new Image).src="/mp/appmsgreport?action=appmsg_recom&type=1&__biz="+biz+"&ascene="+(window.ascene||-1)+"&mid="+mid+"&idx="+idx+"&sn="+sn+"&product_id="+o.product_id+"&order="+o.order+"&r="+Math.random());
}
}
}
var o=e("biz_common/dom/event.js"),r=e("common/utils.js");
if(document.getElementsByClassName){
for(var n=document.getElementsByClassName("js_product_section"),d=document.getElementsByClassName("js_product_a"),i=[],s=0;s<n.length;++s){
var a=n[s];
a.dataset&&a.dataset.product_id&&a.dataset.order&&i.push({
dom:a,
offsetTop:a.offsetTop,
product_id:a.dataset.product_id||"",
order:a.dataset.order||"",
isReport:!1
});
}
i.length>0&&(o.on(window,"scroll",t),t());
for(var s=0;s<d.length;++s)!function(e){
o.on(e,"click",function(){
var t=e.dataset||{};
return(new Image).src="/mp/appmsgreport?action=appmsg_recom&type=2&__biz="+biz+"&ascene="+(window.ascene||-1)+"&mid="+mid+"&idx="+idx+"&sn="+sn+"&product_id="+(t.product_id||"")+"&order="+(t.order||"")+"&r="+Math.random(),
t.href?(setTimeout(function(){
location.href="http://mp.weixinbridge.com/mp/wapredirect?url="+encodeURIComponent(t.href)+"&action=appmsg_redirect&uin="+uin+"&biz="+biz+"&mid="+mid+"&idx="+idx+"&scene=0";
},300),!1):!1;
},!0);
}(d[s]);
}
});define("appmsg/review_image.js",["biz_common/dom/event.js","biz_wap/jsapi/core.js","biz_common/utils/url/parse.js","appmsg/log.js","biz_wap/utils/ajax.js","biz_wap/utils/mmversion.js","appmsg/cdn_img_lib.js"],function(e){
"use strict";
function t(e,t,o,a){
var i={
current:e,
urls:t,
currentInfo:{
url:e,
data:o,
pos:a
}
};
console.log("imagePreview request",i),console.log("previewFlag",g),g||(g=!0,r.invoke("imagePreview",i,function(e){
console.log("imagePreview response",e),window.__addIdKeyReport&&window.__addIdKeyReport("28307","2");
}),setTimeout(function(){
g=!1;
},500),d("[Appmsg] click image, src: "+e));
}
function o(e,t){
s({
url:"/mp/rewardappmsgreport",
data:{
__biz:window.biz||"",
mid:window.mid||"",
idx:window.idx||"",
oper:t||"",
cdn_url:e||"",
ascene:window.ascene||-1
},
type:"POST",
dataType:"json",
async:!0
});
}
function a(e){
var a=[],r=e.container,d=e.imgs||[];
if(r)for(var s=r.getElementsByTagName("img")||[],g=0,l=s.length;l>g;g++)d.push(s.item(g));
for(var c=p.isIOS&&1==window._copyright_stat&&1==window.is_need_reward,m=0,g=0,l=d.length;l>g;g++){
var w=d[g],u=w.getAttribute("data-src")||w.getAttribute("src"),h=w.getAttribute("data-type");
if(u&&!u.isGif()&&0!=u.indexOf("data:")){
for(;-1!=u.indexOf("?tp=webp");)u=u.replace("?tp=webp","");
w.dataset&&w.dataset.s&&u.isCDN()&&(u=u.replace(/\/640$/,"/0"),u=u.replace(/\/640\?/,"/0?")),
u.isCDN()&&(u=n.addParam(u,"wxfrom","3",!0)),u=e.is_https_res?u.http2https():u.https2http(),
h&&(u=n.addParam(u,"wxtype",h,!0)),a.push(u),"1"!=w.getAttribute("data-nopreviewclick")&&!function(e){
p.isAndroid&&w.setAttribute("data-wxsrc",e),i.on(w,"click",function(i){
if(i.stopPropagation(),!(i&&i.target&&i.target.className&&i.target.className.indexOf("img_loadederror")>-1)){
if("function"==typeof window.__addIdKeyReport&&window.__addIdKeyReport("110644",2),
window.getComputedStyle){
for(var r=i.target,n=r.getBoundingClientRect(),d=.15*n.width,s=.15*n.height,g=!0;r&&"body"!=r.nodeName.toLowerCase();){
var l=window.getComputedStyle(r,null),w=parseInt(l.getPropertyValue("opacity")),u=l.getPropertyValue("filter"),h=l.getPropertyValue("visibility"),f=l.mixBlendMode;
if(1!=w||"visible"!=h||u.indexOf("opacity")>=0||u.indexOf("blur")>=0||f&&"normal"!=f){
g=!1;
break;
}
var b=r.getBoundingClientRect();
if(("hidden"==l.overflow||"hidden"==l.overflowX||"hidden"==l.overflowY)&&(b.left-n.left>d||b.right-n.right<-1*d||b.top-n.top>s||b.bottom-n.bottom<-1*s)){
g=!1;
break;
}
r=r.parentElement;
}
if(!g){
if(console.log("don't try this again"),"function"==typeof window.__addIdKeyReport){
window.__addIdKeyReport("110644",3);
var y=new Image,_="https://badjs.weixinbridge.com/badjs?id=168&level=4&from="+encodeURIComponent(location.href)+"&msg="+encodeURIComponent(e);
y.src=_.slice(0,1024);
}
return!1;
}
}
"undefined"==typeof getComputedStyle&&(window.getComputedStyle=document.body.currentStyle?function(e){
return e.currentStyle;
}:{});
var v=i.target,j=window.getComputedStyle(v),F=v.getBoundingClientRect(),x=document.createElement("canvas");
x.style.width=j.width,x.style.height=j.height,x.width=parseFloat(j.width),x.height=parseFloat(j.height);
var C=x.getContext("2d"),I="";
C.drawImage(v,0,0,parseFloat(j.width),parseFloat(j.height));
try{
I=x.toDataURL();
}catch(i){}
p.isAndroid&&(I=""),t(e,a,I,{
x:F.left-parseFloat(j.paddingLeft)-parseFloat(j.borderLeftWidth),
y:F.top-parseFloat(j.paddingTop)-parseFloat(j.borderTopWidth),
width:F.width-parseFloat(j.paddingLeft)-parseFloat(j.paddingRight)-parseFloat(j.borderLeftWidth)-parseFloat(j.borderRightWidth),
height:F.height-parseFloat(j.paddingTop)-parseFloat(j.paddingBottom)-parseFloat(j.borderTopWidth)-parseFloat(j.borderBottomWidth)
}),c&&0==m&&o(i.target.src,2);
}
});
}(u),w.removeAttribute("data-nopreviewclick");
}
}
if(c){
var f=document.getElementById("js_content"),b=0,y=0;
i.on(f,"touchstart",function(e){
return e&&e.target&&e.target.tagName&&"string"==typeof e.target.tagName&&"IMG"==e.target.tagName.toString().toUpperCase()?(m=+new Date,
b=e.touches[0].pageX,void(y=e.touches[0].pageY)):void(m=0);
}),i.on(f,"touchmove",function(e){
var t=e.touches[0].pageX,o=e.touches[0].pageY;
Math.abs(t-b)>10&&Math.abs(o-y)>10&&(m=0);
}),i.on(f,"touchend",function(e){
0!=m&&(+new Date-m>800&&+new Date-m<6e3?o(e.target.src,1):m=0);
});
}
}
var i=e("biz_common/dom/event.js"),r=e("biz_wap/jsapi/core.js"),n=e("biz_common/utils/url/parse.js"),d=e("appmsg/log.js"),s=e("biz_wap/utils/ajax.js"),p=e("biz_wap/utils/mmversion.js"),g=!1;
return e("appmsg/cdn_img_lib.js"),a;
});define("appmsg/outer_link.js",["biz_common/dom/event.js","appmsg/open_url_with_webview.js","biz_wap/jsapi/core.js","biz_wap/utils/mmversion.js","biz_wap/utils/ajax.js","appmsg/popup_report.js"],function(e){
"use strict";
function t(e){
e.preventDefault();
}
function o(e){
var t=e.innerHTML,o=/<img.*src=[\'\"]/,i=/background-image:(\s*)url\(/,n=/background:[^;"']+url\(/;
return o.test(t)||i.test(t)||n.test(t)?!0:!1;
}
function i(e){
var t=e.innerHTML,o=e.style.fontSize;
return 0===t.trim().length||0===parseFloat(o)?!0:!1;
}
function n(e,t){
var o=e.getElementsByClassName("weui-dialog__bd")[0],i=e.getElementsByClassName("weui-dialog")[0];
if(e.getElementsByClassName("weui-dialog__hd")&&e.getElementsByClassName("weui-dialog__hd").length>0&&i.removeChild(e.getElementsByClassName("weui-dialog__hd")[0]),
t.title&&t.desc){
var n=document.createElement("div");
n.setAttribute("class","weui-dialog__hd");
var r='<strong class="weui-dialog__title">'+t.title+"</strong>";
n.innerHTML=r,o.innerText=t.desc,i.insertBefore(n,o);
}else o.innerText=t.desc;
}
function r(e){
var r=e.container;
if(!r)return!1;
for(var _=r.getElementsByTagName("a")||[],w=0,y=_.length;y>w;++w)!function(r){
var w=_[r],y=w.getAttribute("href");
if(!y)return!1;
var h=0,j=w.innerHTML;
/^[^<>]+$/.test(j)?h=1:/^<img[^>]*>$/.test(j)&&(h=2);
var v=w.getAttribute("data-linktype"),b=w.getAttribute("href");
a.on(w,"tap",function(r){
var a=w.getAttribute("href");
if(!a)return!1;
!!e.changeHref&&!/^https?:\/\/mp\.weixin\.qq\.com\/cgi-bin\//.test(a)&&(a=e.changeHref(a,h)),
r.preventDefault();
var _="";
c[w.getAttribute("data-itemshowtype")]&&(_=c[w.getAttribute("data-itemshowtype")]);
document.getElementById("js_link_dialog_name");
return u[b]&&u[b].subject_name&&"0"===u[b].item_show_type&&u[b].title?n(g,{
title:'即将打开公众号 "'+u[b].subject_name+'" 的'+c[u[b].item_show_type],
desc:f.innerText="《"+u[b].title+"》"
}):u[b]&&u[b].subject_name&&u[b].item_show_type>=0?n(g,{
desc:'即将打开公众号 "'+u[b].subject_name+'" 的'+c[u[b].item_show_type]
}):n(g,{
desc:"即将打开新的页面"
}),r.stopPropagation(),"undefined"==typeof d[b]&&(b.indexOf("mp.weixin.qq.com/s/")>-1||b.indexOf("mp.weixin.qq.com/s?")>-1)?(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_6_1&r="+Math.random():"undefined"==typeof d[b]&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_7_1&r="+Math.random()),
d=function(){
return u[b]&&u[b].item_show_type>=0&&a.indexOf("mp.weixin.qq.com")>-1&&(p.isIOS||p.isAndroid)&&!p.isInMiniProgram&&p.isWechat?1==w.getAttribute("clicked")?!1:(m.invoke("openWebViewUseFastLoad",{
url:a,
item_show_type:u[b].item_show_type,
openType:0,
scene:1
},function(e){
console.log("openWebViewUseFastLoad res: ",e),e&&e.err_msg&&-1==e.err_msg.indexOf("ok")?m.invoke("openUrlWithExtraWebview",{
url:a,
openType:1
},function(e){
w.setAttribute("clicked",0),e&&e.err_msg&&-1==e.err_msg.indexOf("ok")&&(window.location.href=url);
}):(w.setAttribute("clicked",0),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28839_37_1");
}),!1):void(p.isInMiniProgram?location.href=a:p.isAndroid||p.isIOS?s(a,{
sample:1,
reject:function(){
location.href=a;
}
}):location.href=a);
},("1"===v||o(w)||i(w))&&l.report([2,l.getRedirectType(b),"",img_popup?1:0,window.source,l.getUrlData(b)]),
("1"===v||o(w)||i(w))&&img_popup?(console.log("tap img link"),g.style.display="block",
g._url=b,(o(w)||i(w))&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_8_1&r="+Math.random(),
g._type="OTHER"),document.querySelector("body").addEventListener("touchmove",t,{
passive:!1
})):d(),!1;
},!0),a.on(w,"click",function(e){
("1"===v||"2"===v||o(w)||i(w))&&img_popup&&(e.preventDefault(),e.stopPropagation());
},!0);
}(w);
}
var a=e("biz_common/dom/event.js"),s=e("appmsg/open_url_with_webview.js"),m=e("biz_wap/jsapi/core.js"),p=e("biz_wap/utils/mmversion.js"),l=(e("biz_wap/utils/ajax.js"),
e("appmsg/popup_report.js")),c={
0:"文章",
11:"文章",
8:"图片",
7:"语音",
5:"视频"
},u={};
if("undefined"!=typeof jumpInfo)for(var _=0;_<jumpInfo.length;_++)u[jumpInfo[_].url]={
title:jumpInfo[_].title,
item_show_type:jumpInfo[_].item_show_type,
subject_name:jumpInfo[_].subject_name,
link_type:jumpInfo[_].link_type
};
var d=function(){},g=document.getElementById("js_link_dialog"),f=(document.getElementById("js_link_dialog_head"),
document.getElementById("js_link_dialog_body"));
return a.on(document.getElementById("js_link_dialog_ok"),"tap",function(e){
e.stopPropagation(),e.preventDefault(),"OTHER"===g._type&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_10_1&r="+Math.random()),
l.report([4,l.getRedirectType(g._url),"",img_popup?1:0,window.source,l.getUrlData(g._url)]),
document.querySelector("body").removeEventListener("touchmove",t),d&&d(),g.style.display="none";
}),a.on(document.getElementById("js_link_dialog_cancel"),"tap",function(e){
e.stopPropagation(),e.preventDefault(),document.querySelector("body").removeEventListener("touchmove",t),
"OTHER"===g._type&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_9_1&r="+Math.random()),
g.style.display="none",l.report([3,l.getRedirectType(g._url),"",img_popup?1:0,window.source,l.getUrlData(g._url)]);
}),r;
});define("appmsg/copyright_report.js",["common/utils.js","biz_common/dom/event.js"],function(o){
"use strict";
function i(o){
var i=["/mp/copyrightreport?action=report&biz=",biz,"&scene=",o.scene,"&user_uin=",user_uin,"&uin=",uin,"&key=",key,"&pass_ticket=",pass_ticket,"&mid=",window.mid,"&idx=",window.idx,"&source_biz=",window.source_biz,"&source_mid=",window.source_mid,"&source_idx=",window.source_idx,"&card_version=2","&show_appmsg_scene=",window.source,"&session_id=",window.sessionid,"&has_recommend_msg=",window.hasRecommendMsg,"&t=",Math.random()].join("");
window.isSg&&(i+="&from=sougou");
var e=new Image;
e.src=i.substr(0,1024);
}
function e(){
var o=__appmsgCgiData;
if("2"==o.copyright_stat){
for(var i=r("copyright_info"),e=r("js_article");i&&e!==i;)c.copyright_top+=i.offsetTop,
i=i.offsetParent;
t.on(window,"scroll",n),n();
}
}
function n(){
var o=window.pageYOffset||document.documentElement.scrollTop;
o+s.getInnerHeight()>c.copyright_top&&(i({
scene:"1",
card_pos:"0"
}),t.off(window,"scroll",n),n=c.copyright_top=null);
}
function r(o){
return document.getElementById(o);
}
var s=o("common/utils.js"),t=o("biz_common/dom/event.js"),c={
copyright_top:0
};
return{
card_click_report:i,
card_pv_report:e
};
});define("appmsg/async.js",["biz_wap/ui/weui.js","biz_common/utils/string/html.js","appmsg/reward_utils.js","appmsg/pay_read_utils.js","appmsg/pay_report_utils.js","pages/create_txv.js","pages/video_ctrl.js","biz_common/utils/url/parse.js","appmsg/img_copyright_tpl.html.js","appmsg/appmsgext.js","appmsg/share_tpl.html.js","biz_common/dom/event.js","biz_wap/utils/ajax.js","biz_wap/jsapi/core.js","biz_common/tmpl.js","complain/localstorage.js","appmsg/log.js","rt/appmsg/getappmsgext.rt.js","a/a_utils.js","appmsg/related_article.js","appmsg/set_font_size.js","biz_wap/utils/device.js","biz_wap/utils/mmversion.js","pages/version4video.js","appmsg/like.js","appmsg/comment.js","appmsg/iframe.js","redpackage/redpacketcover.js","appmsg/more_read.js"],function(e){
"use strict";
function t(){
for(var t=document.getElementsByTagName("iframe"),a=[],r=0,n=t.length;n>r;++r)a.push(t[r]);
t=null;
var o=document.getElementById("js_content"),s=o.offsetWidth,d=s/c.getRatio();
window.logs.video_cnt=0;
for(var r=0,n=a.length;n>r;++r){
var _=a[r],m=_.getAttribute("data-src")||"",p=_.getAttribute("src")||m;
if(p){
var l=e("pages/version4video.js");
if(0==p.indexOf("http://z.weishi.com/weixin/player.html"))p=p.replace(/width=\d+/g,"width="+s),
p=p.replace(/height=\d+/g,"height="+d),_.width=s,_.height=d,_.style.setProperty&&(_.style.setProperty("width",s+"px","important"),
_.style.setProperty("height",d+"px","important")),_.setAttribute("src",p),window.__addIdKeyReport&&window.__addIdKeyReport("28307",10),
window.logs.video_cnt++;else{
if(/http(s)*\:\/\/v\.qq\.com\/iframe\/(preview|player)\.html\?/.test(p)){
if(!l.isShowMpVideo()){
var w;
w=i(h?_:_),w&&x.push(w),"function"==typeof window.__addIdKeyReport&&(window.__addIdKeyReport("28307",10),
l.device.inWechat&&l.device.inWindowWechat?window.__addIdKeyReport("110644",0):l.device.inWechat&&l.device.inMacWechat&&window.__addIdKeyReport("110644",1));
}
window.logs.video_cnt++;
continue;
}
/^http(s)*\:\/\/mp\.weixin\.qq\.com\/mp\/readtemplate\?t=pages\/video_player_tmpl/.test(p)&&window.logs.video_cnt++;
}
}
}
x.length>0&&"function"==typeof window.__getVideoWh&&y.on(window,"resize",function(){
try{
for(var e=0,t=x.length;t>e;e++){
var i=x[e],a=i.playerObj;
if(a){
var r=window.__getVideoWh(i);
i.style.width=r.w+"px",i.style.height=r.h+"px",a.resize({
width:r.vw,
height:r.vh
});
}
}
}catch(n){}
},!1);
}
function i(e){
var t=e.getAttribute("data-src")||e.getAttribute("src"),i=p.getQuery("vid",t),r=e.getAttribute("data-vw"),n=e.getAttribute("data-vh"),o=e.getAttribute("data-ratio"),s=document.createElement("span");
s.setAttribute("data-ratio",o),s.id="js_tx_video_container_"+Math.random(),s.className="js_tx_video_container",
s.style.cssText=e.style.cssText,s.style.display="none";
var d=e.parentNode;
return d?(d.lastChild===e?d.appendChild(s):d.insertBefore(s,e.nextSibling),m.createTxVideo({
containerId:s.id,
vid:i,
width:r,
height:n,
autoplay:!1,
allowFullScreen:!0,
onSuccess:function(e){
s.playerObj=e.player,a(s,i),s.style.display="block";
},
onError:function(){}
}),d.removeChild(e),s):void 0;
}
function a(e,t){
if(t&&e){
var i=e.parentNode;
if(i){
for(var a=[],r=0,n=i.children.length;n>r;r++){
var o=i.children[r];
o.className.indexOf("img_loading")>=0&&o.getAttribute("data-vid")==t&&a.push(o);
}
for(var r=0,n=a.length;n>r;r++)i.removeChild(a[r]);
e.style.display="block";
}
}
}
function r(e){
if(e&&e.img_copy_info&&e.img_copy_info.list){
for(var t={},i=e.img_copy_info.list,a=window.__appmsgCgiData.copyright_stat,r=window.__appmsgCgiData.source_biz,n=0,o=i.length;o>n;n++){
var s=i[n];
if(2==s.type){
if(2==a&&r==s.source_uin)continue;
t[s.img_url]={
source_nickname:s.source_nickname,
source_uin:s.source_uin,
source_encode_biz:s.source_encode_biz||""
};
}
}
for(var d=document.getElementsByTagName("img"),n=0,o=d.length;o>n;n++){
var s=d[n],_=s.getAttribute("data-src")||s.getAttribute("data-backsrc")||"";
if(t[_]){
var m=document.createElement("div");
m.innerHTML=b.tmpl(l,t[_]);
{
var c=m.children[0],p=s.parentNode,w=p.insertBefore(c,s),u=w.children[0];
(function(e,t){
y.on(t,"click",function(){
var t="https://mp.weixin.qq.com/mp/profile_ext?action=home&__biz="+e.source_encode_biz+"&scene=112#wechat_redirect";
return-1!=navigator.userAgent.indexOf("WindowsWechat")||-1!=navigator.userAgent.indexOf("Mac OS")?(location.href=t,
!1):(f.invoke("openUrlWithExtraWebview",{
url:t,
openType:1
},function(e){
-1==e.err_msg.indexOf("ok")&&(location.href=t);
}),!1);
});
})(t[_],u);
}
w.insertBefore(s,u);
}
}
}
}
function n(t){
var i=t.appmsgstat||{},a=t.paySubscribeInfo||{};
if(window.paySubscribeInfo=a,window.isFans=t.is_fans,window.appmsgstat||(window.appmsgstat=i),
i.show){
{
var r=document.getElementById("js_read_area3"),n=document.getElementById("like3"),o=document.getElementById("like_old"),_=document.getElementById("likeNum3"),m=document.getElementById("likeNum_old"),c=document.getElementById("readNum3");
document.getElementById("js_like_title");
}
if(!(r&&n&&_&&c))return;
var p,l,w=e("appmsg/like.js");
if(1==appmsg_like_type?(p=o,l=m):(p=n,l=_),i.liked=window.is_temp_url?window.liked:i.liked,
w.showReadNum({
show:!0,
readAreaDom:r,
readNumDom:c,
readAreaDisplayValue:window.isPaySubscribe?"none":"block",
readNum:window.is_temp_url?window.read_num:i.read_num
}),f.invoke("handleHaokanAction",{
imgUrl:ori_head_img_url?ori_head_img_url:"",
link:msg_link.html(!1),
desc:msg_desc?msg_desc:"",
title:msg_title?msg_title.htmlDecode():"",
action:"update_recommend_status",
permission:i.like_disabled||2!==appmsg_like_type?0:1,
recommend:i.liked?1:0
},function(){}),!i.like_disabled){
var g=1===appmsg_like_type?"praised":"like_btn_liked";
w.showLikeNum({
show:!0,
likeAreaDom:p,
likeNumDom:l,
liked:i.liked,
className:g,
likeAreaDisplayValue:"inline",
likeNum:window.is_temp_url?window.like_num:i.like_num
}),w.initLikeEvent({
likeAreaDom:p,
likeNumDom:l,
className:g,
prompted:i.prompted,
biz:window.biz,
mid:window.mid,
idx:window.idx,
appmsgid:window.appmsgid,
itemidx:window.itemidx,
is_temp_url:window.is_temp_url,
showType:i.style
});
}
}
var h=document.getElementById("js_share_appmsg");
t.share_redirect_url&&h&&(window._share_redirect_url=t.share_redirect_url,h.innerHTML=b.tmpl(u,{
url:t.share_redirect_url
})),1===t.comment_enabled&&!function(){
var i=e("appmsg/comment.js");
(!window.isPaySubscribe||window.isPaySubscribe&&window.isPaid)&&hasRelatedArticleInfo&&!S?E=function(e){
return function(){
i.initComment(e);
};
}(t):i.initComment(t);
}(),j.setBackgroundClass(),s.init(t.reward,{
reward_entrance_enable_for_preview:t.reward_entrance_enable_for_preview,
reward_wording:t.reward_wording,
reward_author_head:t.reward_author_head
}),window.isPaySubscribe&&d.init(a);
var v=document.getElementById("js_cmt_container");
if(1==t.comment_entrance_enable_for_preview&&window.is_temp_url&&v&&(v.style.display="block"),
t.comment_entrance_enable_for_preview&&(document.getElementById("js_preview_cmt")&&(document.getElementById("js_preview_cmt").style.display="block"),
y.on(document.getElementById("js_preview_cmt_write"),"tap",function(e){
e.preventDefault(),window.weui.alert("预览状态下无法操作");
})),t.comment_enabled&&v&&(v.style.display="block"),A.isIOS&&"block"===v.style.display&&location.href.match(/fontScale=\d+/)&&I.os.ipad&&I.os.getNumVersion()>=13){
var k=location.href.match(/fontScale=(\d+)/);
z(v,parseFloat(k[1])/100);
}
}
function o(){
var t=0,i="27613",a="50";
w.getData({
biz:biz,
appmsg_type:appmsg_type,
mid:mid,
sn:sn,
idx:idx,
scene:source,
title:msg_title,
ct:ct,
abtest_cookie:abtest_cookie,
devicetype:devicetype,
version:window.clientversion,
is_need_ticket:x&&x.length>0?1:0,
is_need_ad:0,
comment_id:comment_id,
is_need_reward:is_need_reward,
both_ad:0,
reward_uin_count:is_need_reward?3*s.getCountPerLine({
can_reward:!0
})-1:0,
send_time:window.send_time||"",
msg_daily_idx:msg_daily_idx,
item_show_type:window.item_show_type,
is_original:t,
is_only_read:is_only_read,
req_id:window.req_id||"",
pass_ticket:pass_ticket,
is_temp_url:window.is_temp_url||0,
more_read_type:more_read_type||0,
rtId:i,
rtKey:a,
appmsg_like_type:window.appmsg_like_type,
is_pay_subscribe:window.isPaySubscribe,
pay_subscribe_uin_count:window.isPaySubscribe?3*d.getCountPerLine():0,
has_red_packet_cover:window.__appmsgCgiData.has_red_packet_cover,
onSuccess:function(t){
if(t)try{
if(window.__second_open__&&t.pay_subscribe_info&&1*t.pay_subscribe_info.is_paid!=isPaid)return _.report110809(11),
void f.invoke("handleMPPageAction",{
action:"paySuccess",
fullUrl:window.location.href,
itemShowType:window.item_show_type
},function(e){
_.report110809(e.err_msg.indexOf("ok")>-1?19:20),window.localStorage&&window.localStorage.setItem&&window.localStorage.setItem("isPaid-"+window.biz+"-"+window.mid+"-"+window.idx,"1"),
window.location.href=window.location.href+"&r="+Math.random()+"#wechat_redirect";
});
if(t&&t.base_resp&&t.base_resp.wxtoken&&(window.wxtoken=t.base_resp.wxtoken),window.fromWeixinCached&&e("appmsg/iframe.js"),
r(t),t.ret)return;
if(t.red_packet_cover_data&&t.red_packet_cover_data.cover_uri_data&&t.red_packet_cover_data.cover_uri_data.length>0){
var o=e("redpackage/redpacketcover.js");
o.render({
list:t.red_packet_cover_data.cover_uri_data
});
}
var s=document.getElementById("js_more_read_area");
s&&t&&t.more_read_list&&t.more_read_list.length&&e("appmsg/more_read.js")(s,t.more_read_list),
n({
appmsgstat:t.appmsgstat,
comment_enabled:t.comment_enabled,
comment_count:t.comment_count,
friend_comment_enabled:t.friend_comment_enabled,
only_fans_can_comment:t.only_fans_can_comment,
only_fans_days_can_comment:t.only_fans_days_can_comment,
is_fans_days:t.is_fans_days,
reward:{
reward_total:t.reward_total_count,
reward_head_imgs:t.reward_head_imgs||[],
can_reward:t.can_reward,
user_can_reward:t.user_can_reward,
reward_qrcode_ticket:t.reward_qrcode_ticket,
timestamp:t.timestamp,
reward_author_head:t.reward_author_head,
rewardsn:t.rewardsn,
scene:source,
is_need_reward:is_need_reward,
title:msg_title,
author_id:author_id,
appmsgextRtId:i,
appmsgextRtKey:a
},
reward_entrance_enable_for_preview:t.reward_entrance_enable_for_preview,
reward_wording:t.reward_wording,
reward_author_head:t.reward_author_head,
comment_entrance_enable_for_preview:t.comment_entrance_enable_for_preview,
share_redirect_url:t.share_redirect_url||"",
logo_url:t.logo_url,
nick_name:t.nick_name,
is_fans:t.is_fans,
paySubscribeInfo:t.pay_subscribe_info
});
}catch(d){
v("[Appmsg] error parse async data, biz="+biz+", mid="+mid);
var m=new Image;
return m.src=("http://mp.weixin.qq.com/mp/jsreport?1=1&key=1&content=biz:"+biz+",mid:"+mid+",uin:"+uin+"[key1]"+encodeURIComponent(d.toString())+"&r="+Math.random()).substr(0,1024),
void(console&&console.error(d));
}
},
onError:function(){
var e=new Image;
e.src="http://mp.weixin.qq.com/mp/jsreport?1=1&key=2&content=biz:"+biz+",mid:"+mid+",uin:"+uin+"[key2]ajax_err&r="+Math.random();
}
});
}
e("biz_wap/ui/weui.js"),e("biz_common/utils/string/html.js");
var s=e("appmsg/reward_utils.js"),d=e("appmsg/pay_read_utils.js"),_=e("appmsg/pay_report_utils.js"),m=e("pages/create_txv.js"),c=e("pages/video_ctrl.js"),p=e("biz_common/utils/url/parse.js"),l=e("appmsg/img_copyright_tpl.html.js"),w=e("appmsg/appmsgext.js"),u=e("appmsg/share_tpl.html.js"),g=navigator.userAgent,h=-1!=g.indexOf("MicroMessenger"),y=(-1!=navigator.userAgent.indexOf("WindowsWechat"),
e("biz_common/dom/event.js")),f=(e("biz_wap/utils/ajax.js"),e("biz_wap/jsapi/core.js")),b=e("biz_common/tmpl.js"),v=(e("complain/localstorage.js"),
e("appmsg/log.js")),j=(e("rt/appmsg/getappmsgext.rt.js"),e("a/a_utils.js")),k=e("appmsg/related_article.js"),x=[],z=e("appmsg/set_font_size.js"),I=e("biz_wap/utils/device.js"),A=e("biz_wap/utils/mmversion.js"),S=!1;
t();
var E=function(){};
o(),(!window.isPaySubscribe||window.isPaySubscribe&&window.isPaid)&&hasRelatedArticleInfo&&k(function(e,t){
S=!0,"error"==e?E():(E(),t());
});
});define("biz_wap/ui/lazyload_img.js",["biz_wap/utils/mmversion.js","biz_common/dom/event.js","biz_common/dom/attr.js","biz_common/ui/imgonepx.js"],function(t){
"use strict";
function i(){
var t=this.images;
if(!t||t.length<=0)return!1;
var i=window.pageYOffset||document.documentElement.scrollTop,e=window.innerHeight||document.documentElement.clientHeight,o=this.offset||60,n=0;
if("wifi"==window.networkType){
var s={
bottom:1,
top:1
};
this.lazyloadHeightWhenWifi&&(s=this.lazyloadHeightWhenWifi()),o=Math.max(s.bottom*e,o),
n=Math.max(s.top*e,n);
}
for(var r=+new Date,c=[],d=this.sw,f=this,g=-1,u=0,p=t.length;p>u;u++)!function(t,i){
var s=t.el.getBoundingClientRect(),r=t.src;
if(r){
(r.match(/\:\/\/[^\/]+\/mmbiz\//)&&r.indexOf("wx_fmt=gif")>-1||r.match(/\:\/\/[^\/]+\/mmbiz_gif\//))&&g++;
var f=n,u=o;
(r.match(/\:\/\/[^\/]+\/mmbiz\//)&&r.indexOf("wx_fmt=gif")>-1||r.match(/\:\/\/[^\/]+\/mmbiz_gif\//))&&l&&(f=0,
u=60),!t.show&&(s.top<=0&&s.top+s.height+f>=0||s.top>0&&s.top<e+u)&&(i.inImgRead&&(s.top<=0&&s.top+s.height>=0||s.top>0&&s.top<e)&&i.inImgRead(r,networkType),
i.changeSrc&&(r=i.changeSrc(t.el,r,g)),t.el.onerror=function(){
var e=this;
!!i.onerror&&i.onerror(t.el.src,e);
},t.el.onload=function(){
var e=this;
if("data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg=="!=e.src){
var o=e.getAttribute("data-forceheight");
o?(e.removeAttribute("data-forceheight"),h(e,"height",o,"important")):h(e,"height","auto","important"),
e.getAttribute("_width")?h(e,"width",e.getAttribute("_width"),"important"):h(e,"width","auto","important"),
!!i.onload&&i.onload(t.el.src,e);
}
},m(t.el,"src",r),c.push(r),t.show=!0,h(t.el,"visibility","visible","important")),
a.isWp&&1*t.el.width>d&&(t.el.width=d);
}
}(t[u],f);
c.length>0&&this.detect&&this.detect({
time:r,
loadList:c,
scrollTop:i
});
}
function e(){
var t=document.getElementsByTagName("img"),e=[],o=this.container,n=this.attrKey||"data-src",a=o.offsetWidth,s=0,r=this.imgOccupied||!1,l=this.crossOrigin||!1;
o.currentStyle?s=o.currentStyle.width:"undefined"!=typeof getComputedStyle&&(s=getComputedStyle(o).width),
this.sw=1*s.replace("px","");
for(var d=0,f=t.length;f>d;d++){
var g=t.item(d),u=m(g,n),p=m(g,"src");
if(u&&!(p&&p.indexOf("data:image/gif;base64")<0)){
var w=100;
if(g.dataset&&g.dataset.ratio){
var A=1*g.dataset.ratio,b=1*g.dataset.w||a;
"number"==typeof A&&A>0?(b=a>=b?b:a,w=b*A,r||(g.style.width&&g.setAttribute("_width",g.style.width),
h(g,"width",b+"px","important"),h(g,"visibility","visible","important"),g.setAttribute("src",c))):h(g,"visibility","hidden","important");
}else h(g,"visibility","hidden","important");
r||h(g,"height",w+"px","important"),l&&-1==u.indexOf("mmsns.qpic.cn")&&!(u.match(/\:\/\/[^\/]+\/mmbiz\//)&&u.indexOf("wx_fmt=gif")>-1||u.match(/\:\/\/[^\/]+\/mmbiz_gif\//))&&(g.crossOrigin="anonymous"),
e.push({
el:g,
src:u,
height:w,
show:!1
});
}
}
this.images=e,i.call(this);
}
function o(t){
if(this.__called_first_time)i.call(this,t),this.__called_first_time=!1;else if(!this.debounce){
this.debounce=!0;
var e=this;
setTimeout(function(){
i.call(e,t),e.debounce=!1;
},500);
}
}
function n(t){
s.on(window,"scroll",function(i){
o.call(t,i);
}),setTimeout(function(){
e.call(t,{});
},0),s.on(document,"touchmove",function(i){
o.call(t,i);
}),t.__called_first_time=!0,o.call(t,{});
}
var a=t("biz_wap/utils/mmversion.js"),s=t("biz_common/dom/event.js"),r=t("biz_common/dom/attr.js"),m=r.attr,h=r.setProperty,c=t("biz_common/ui/imgonepx.js"),l=!0;
return n;
});define("biz_common/log/jserr.js",[],function(){
function e(e,n){
return e?(r.replaceStr&&(e=e.replace(r.replaceStr,"")),n&&(e=e.substr(0,n)),encodeURIComponent(e.replace("\n",","))):"";
}
var r={};
return window.onerror=function(n,o,t,c,i){
return"Script error."==n||o?"undefined"==typeof r.key||"undefined"==typeof r.reporturl?!0:void setTimeout(function(){
c=c||window.event&&window.event.errorCharacter||0;
var l=[];
if(l.push("msg:"+e(n,100)),o&&(o=o.replace(/[^\,]*\/js\//g,"")),l.push("url:"+e(o,200)),
l.push("line:"+t),l.push("col:"+c),i&&i.stack)l.push("info:"+e(i.stack.toString(),200));else if(arguments.callee){
for(var s=[],u=arguments.callee.caller,a=3;u&&--a>0&&(s.push(u.toString()),u!==u.caller);)u=u.caller;
s=s.join(","),l.push("info:"+e(s,200));
}
var p=new Image;
if(p.src=(r.reporturl+"&key="+r.key+"&content="+l.join("||")).substr(0,1024),window.console&&window.console.log){
var f=l.join("\n");
try{
f=decodeURIComponent(f);
}catch(d){}
console.log(f);
}
},0):!0;
},function(e){
r=e;
};
});define("appmsg/share.js",["biz_common/utils/string/html.js","appmsg/cdn_img_lib.js","biz_common/jquery.md5.js","biz_common/dom/event.js","biz_common/utils/url/parse.js","biz_wap/utils/mmversion.js","appmsg/appmsg_report.js","appmsg/malicious_wording.js","biz_wap/utils/ajax.js","biz_wap/jsapi/core.js"],function(e){
"use strict";
function i(e,i,n){
var t="",o="";
try{
""!=tid&&(o="tid="+tid+"&aid=54");
var s=e.split("?")[1]||"";
if(s=s.split("#")[0],""==s);else{
var m=[s,"mpshare=1","scene="+i,"srcid="+srcid,"sharer_sharetime="+n,"sharer_shareid="+r];
""!=o&&m.push(o),s=m.join("&"),t=e.split("?")[0]+"?"+s+"#"+(e.split("#")[1]||"");
}
}catch(a){
t="";
}
return t||(t=location.href+"#wechat_redirect",(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_47_1&lc=1&log0=[share_link]["+encodeURIComponent(location.href)+"]["+encodeURIComponent(e)+"]["+encodeURIComponent(msg_link)+"]"),
t;
}
function n(e,i,n,t){
m.shareReport({
link:e,
action_type:n,
sharer_sharetime:t,
sharer_shareid:r
});
}
function t(e,i){
return e.isCDN()&&(e=o.addParam(e,"wxfrom",i,!0)),e;
}
e("biz_common/utils/string/html.js"),e("appmsg/cdn_img_lib.js"),e("biz_common/jquery.md5.js");
var o=(e("biz_common/dom/event.js"),e("biz_common/utils/url/parse.js")),s=e("biz_wap/utils/mmversion.js"),m=e("appmsg/appmsg_report.js"),a=e("appmsg/malicious_wording.js"),r=(e("biz_wap/utils/ajax.js"),
window.md5(window.user_uin)),c=e("biz_wap/jsapi/core.js");
c.call("hideToolbar"),c.call("showOptionMenu");
var l=msg_title.htmlDecode(),_=(msg_source_url.htmlDecode(),""),u=cdn_url_1_1||msg_cdn_url||ori_head_img_url||round_head_img,d=u,p=msg_link.htmlDecode(),l=msg_title.htmlDecode(),h=msg_desc.htmlDecode();
h=h||"",h=h.replace(/<br\/>/g,"\n"),idx>1&&document.getElementById("js_content")&&1446652800>ct&&(h=document.getElementById("js_content").innerHTML.replace(/<\/?[^>]*\/?>/g,"").htmlDecode().replace(/^(\s*)|(\s*)$/g,"").substr(0,54)),
u.isCDN()&&(u=u.replace(/\/0$/,"/300"),u=u.replace(/\/0\?/,"/300?")),d.isCDN()&&(d=d.replace(/\/0$/,"/640"),
d=d.replace(/\/0\?/,"/640?")),malicious_title_reason_id&&(l=a.maliciousTitleMap[malicious_content_type][malicious_title_reason_id]||l,
h=a.maliciousDescMap[malicious_content_type][malicious_title_reason_id]||h,1!=malicious_content_type&&(u="https://mmbiz.qlogo.cn/mmbiz_png/cVgP5bCElFiayFgbgEB9iaDt7hLicfz9RrXGM0LpaQ0TUic2gP7lbbqU3jCD8ibonicgIa3p99yjx1f1P26HChraeRUg/0?wx_fmt=png")),
"1"==is_limit_user&&c.call("hideOptionMenu"),window.is_temp_url&&c.invoke("hideMenuItems",{
menuList:["menuItem:share:timeline","menuItem:share:qq","menuItem:share:weiboApp","menuItem:share:facebook","menuItem:share:qzone","menuitem:share:weibo","menuItem:share:WeiboApp","menuItem:share:QZone","menuitem:facebook","menuItem:copyUrl","menuItem:share:email","menuitem:copy_url","menuitem:share:haokan"]
},function(){});
var g="https://res.wx.qq.com/op_res/Fwh9olR917lxUMxpJVM5sCCyrQOJSm68IEt-HfL7vpc5-_etzmyuLg1kPdU6RNRX";
c.on("menu:share:appmessage",function(e){
if(window.is_wash){
var o=Date.now();
c.invoke("sendAppMessage",{
img_url:g,
img_width:"640",
img_height:"640",
link:i(p,s,o),
desc:"你可以阅读以下原创作者的内容",
title:"原文存在洗稿行为"
},function(){
n(p,fakeid,s,o);
});
}else{
var s=1,m=t(u,"1");
e&&"favorite"==e.scene&&(s=24,m=t(u,"4")),1==malicious_content_type&&(m="https://mmbiz.qlogo.cn/mmbiz_png/cVgP5bCElFiayFgbgEB9iaDt7hLicfz9RrXGM0LpaQ0TUic2gP7lbbqU3jCD8ibonicgIa3p99yjx1f1P26HChraeRUg/0?wx_fmt=png");
var o=Date.now();
c.invoke("sendAppMessage",{
appid:_,
img_url:m,
img_width:"640",
img_height:"640",
link:i(p,s,o),
desc:h,
title:l
},function(){
n(p,fakeid,s,o);
});
}
}),c.on("menu:share:timeline",function(){
if(window.is_wash){
var e=Date.now();
c.invoke("shareTimeline",{
img_url:g,
img_width:"640",
img_height:"640",
link:i(p,2,e),
desc:"",
title:"原文存在洗稿行为，你可以阅读以下原创作者的内容"
},function(){
n(p,fakeid,2,e);
});
}else{
var o=u;
s.isIOS||(o=t(u,"2"));
var e=Date.now();
c.invoke("shareTimeline",{
img_url:o,
img_width:"640",
img_height:"640",
link:i(p,2,e),
desc:h,
title:l
},function(){
n(p,fakeid,2,e);
});
}
});
c.on("menu:share:weiboApp",function(){
var e=Date.now();
c.invoke("shareWeiboApp",{
img_url:u,
link:i(p,3,e),
title:l
},function(){
n(p,fakeid,3,e);
});
}),c.on("menu:share:facebook",function(){
var e=Date.now();
n(p,fakeid,7,e),c.invoke("shareFB",{
img_url:d,
img_width:"640",
img_height:"640",
link:i(p,43,e),
desc:h,
title:l
},function(){});
}),c.on("menu:share:QZone",function(){
var e=t(u,"6"),o=Date.now();
n(p,fakeid,5,o),c.invoke("shareQZone",{
img_url:e,
img_width:"640",
img_height:"640",
link:i(p,22,o),
desc:h,
title:l
},function(){});
}),c.on("menu:share:qq",function(){
var e=t(u,"7"),o=Date.now();
n(p,fakeid,5,o),c.invoke("shareQQ",{
img_url:e,
img_width:"640",
img_height:"640",
link:i(p,23,o),
desc:h,
title:l
},function(){});
}),c.on("menu:share:email",function(){
var e=Date.now();
n(p,fakeid,5,e),c.invoke("sendEmail",{
content:i(p,5,e),
title:l
},function(){});
}),c.on("onArticleReadingBtnClicked",function(e){
console.log("argv",e),location.href="https://mp.weixin.qq.com/mp/msgvoice?action=ttspage&__biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&sn="+window.sn+"#wechat_redirect";
}),1==window.show_msg_voice&&c.invoke("showMenuItems",{
menuList:["menuItem:readArticle"]
},function(e){
console.log("showMenuItems call",e);
}),c.on("sys:record",function(){
c.invoke("recordHistory",{
link:p,
title:l,
source:nickname,
img_url:u
},function(){});
});
});define("appmsg/cdn_img_lib.js",[],function(){
"use strict";
function t(t){
return!!(t.match(/\:\/\/[^\/]+\/mmbiz\//)&&t.indexOf("wx_fmt=gif")>-1)||!!t.match(/\:\/\/[^\/]+\/mmbiz_gif\//)&&-1==t.indexOf("/s640");
}
function i(t){
return!!(t.match(/\:\/\/[^\/]+\/mmbiz\//)&&t.indexOf("wx_fmt=png")>-1)||!!t.match(/\:\/\/[^\/]+\/mmbiz_png\//);
}
function n(t){
return!!(t.match(/\:\/\/[^\/]+\/mmbiz\//)&&t.indexOf("wx_fmt=jpg")>-1)||!!t.match(/\:\/\/[^\/]+\/mmbiz_jpg\//);
}
function r(t){
return t.indexOf("tp=webp")>-1;
}
function e(t){
return t.indexOf("tp=wxpic")>-1;
}
String.prototype.http2https=function(){
return this.replace(/http:\/\/mmbiz\.qpic\.cn\//g,"https://mmbiz.qpic.cn/");
},String.prototype.https2http=function(){
var t=this.replace(/https:\/\/mmbiz\.qlogo\.cn\//g,"http://mmbiz.qpic.cn/");
return t=t.replace(/https:\/\/mmbiz\.qpic\.cn\//g,"http://mmbiz.qpic.cn/");
},String.prototype.isCDN=function(){
return 0==this.indexOf("http://mmbiz.qpic.cn/")||0==this.indexOf("https://mmbiz.qpic.cn/")||0==this.indexOf("https://mmbiz.qlogo.cn/")||0==this.indexOf("http://res.wx.qq.com/")||0==this.indexOf("https://res.wx.qq.com/");
},String.prototype.nogif=function(){
var i=this.toString();
return t(i)?i.replace(/\/\d+\?/g,"/s640?").replace(/\/\d+\//g,"/s640/").replace(/\/\d+\./g,"/s640.").replace("wx_fmt=gif",""):i;
},String.prototype.isGif=function(){
var i=this.toString();
return t(i);
},String.prototype.isWxpic=function(){
var t=this.toString();
return e(t);
},String.prototype.isWebp=function(){
var t=this.toString();
return r(t);
},String.prototype.canHevc=function(){
var r=this.toString();
return n(r)||i(r)||t(r);
},String.prototype.getImgType=function(){
var p=this.toString();
return t(p)?"gif":r(p)?"webp":e(p)?"wxpic":i(p)?"png":n(p)?"jpg":"unknow";
},String.prototype.getOriginImgType=function(){
var r=this.toString();
return t(r)?"gif":i(r)?"png":n(r)?"jpg":"unknow";
},String.prototype.imgChange640=function(){
var t=this.toString();
t=t.replace(/(\?tp=webp)|(\?tp=wxpic)|(&tp=webp)|(&tp=wxpic)/g,"");
var i=new Date;
return i.setFullYear(2014,9,1),t.isCDN()&&1e3*ct>=i.getTime()&&!t.isGif()&&(t=t.replace(/\/0$/,"/640"),
t=t.replace(/\/0\?/,"/640?"),t=t.replace(/\/0\./,"/640.")),t;
};
});