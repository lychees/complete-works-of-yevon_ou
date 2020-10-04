define("pages/qqmusic_tpl.html.js",[],function(){
return'<span id="qqmusic_main_<#=musicid#>_<#=posIndex#>" class="js_wap_qqmusic db pages_reset music_area <#if(!musicSupport){#> unsupport<#}#>">\n    <span class="tc tips_global unsupport_tips" <#if(show_not_support!==true){#>style="display:none;"<#}#>>\n    当前浏览器不支持播放音乐或语音，请在微信或其他浏览器中播放    </span>\n    <span class="db music_card appmsg_card_context appmsg_card_active">\n            <a id="qqmusic_home_<#=musicid#>_<#=posIndex#>" class="music_card_bd">\n                <span class="music_card_title"><#=music_name#></span>\n                <span class="music_card_desc"><#=singer#></span>\n                <span class="music_card_source <#if(musictype==2){#>music_card_source_kugou<#}#>">\n                  <img src="<#=musicIcon#>" alt=""></span>\n            </a>\n            <span id="qqmusic_play_<#=musicid#>_<#=posIndex#>" class="music_card_ft">\n                <i class="weui-play-btn"></i>\n                <!--\n                <img src="<#=window.icon_qqmusic_default#>" alt="" class="pic_qqmusic_default">\n                -->\n                <img src="<#=albumurl#>" data-autourl="<#=audiourl#>" data-musicid="<#=musicid#>" class="music_card_thumb" alt="">\n            </span>\n    </span>\n</span>\n';
});define("new_video/ctl.js",["common/comm_report.js","biz_wap/utils/ajax.js"],function(e){
"use strict";
var i,n=e("common/comm_report.js");
if(parent==window)i=window;else try{
{
parent.window.location.href;
}
i=parent.window;
}catch(r){
i=window;
}
var t=i.user_uin,a=Math.floor(i.user_uin/100)%20;
t||(a=-1);
var o=function(){
return a>=0;
};
i.__webviewid||(i.__webviewid=+new Date+"_"+Math.ceil(1e3*Math.random()));
var d=function(){
var e=i.mid,n=i.idx,r="";
r=e&&n?e+"_"+n:"";
var a=i.__webviewid,o=[t,r,a].join("_");
return o;
},s=function(i){
if(20>a)try{
var n=i.vid||"",r={};
r.__biz=parent.window.biz||"",r.vid=n,r.clienttime=+new Date;
var t=parent.window.mid,s=parent.window.idx,p="";
p=t&&s?t+"_"+s:n,r.type="undefined"!=typeof i.type?i.type:t&&s?1:2,r.id=p,r.hit_bizuin=i.hit_bizuin||"",
r.hit_vid=i.hit_vid||"",r.webviewid=d(),r.step=i.step||0,r.orderid=i.orderid||0,
r.ad_source=i.ad_source||0,r.traceid=i.traceid||0,r.ext1=i.ext1||"",r.ext2=i.ext2||"",
r.r=Math.random(),r.devicetype=parent.window.devicetype,r.version=parent.window.clientversion,
r.is_gray=o()?1:0,r.mid=t||"",r.idx=s||"",r.url=parent.window.location.href,r.screen_num=i.screen_num||0,
r.screen_height=i.screen_height||0,r.ori_status=i.ori_status||3,r.fromid=i.fromid||0,
r.sessionid=window.sessionid||"",r.appmsg_scene=window.source||(window.cgiData?window.cgiData.scene:0)||0,
!r.appmsg_scene&&r.fromid?r.appmsg_scene=r.fromid:!r.fromid&&r.appmsg_scene&&(r.fromid=r.appmsg_scene),
r.total_range=i.total_range||0,r.current_range=i.current_range||0,r.duration=i.duration||0;
var c=e("biz_wap/utils/ajax.js");
c({
url:"/mp/ad_video_report?action=user_action",
type:"post",
data:r
});
}catch(w){}
},p=function(e){
try{
var i=e.vid||"",r={};
r.BizUin=parent.window.biz||"",r.Vid=i,r.ClientTime=+new Date;
var t=parent.window.mid,a=parent.window.idx,s="";
s=t&&a?t+"_"+a:i,r.Type="undefined"!=typeof e.type?e.type:t&&a?1:2,r.Id=s,r.HitBizUin=parseInt(e.hit_bizuin)||0,
r.HitVid=e.hit_vid||"",r.WebViewId=d(),r.Step=parseInt(e.step,10)||0,r.OrderId=(e.orderid||"").toString(),
r.AdSource=parseInt(e.ad_source,10)||0,r.TraceId=(e.traceid||"").toString(),r.Ext1=(e.ext1||"").toString(),
r.Ext2=(e.ext2||"").toString(),r.r=Math.random(),r.DeviceType=parent.window.devicetype,
r.ClientVersion=parseInt(parent.window.clientversion),r.IsGray=o()?1:0,r.msgid=parseInt(t,10)||0,
r.itemidx=parseInt(a,10)||0,r.Url=parent.window.location.href,r.ScreenNum=parseInt(e.screen_num,10)||0,
r.ScreenHeight=parseInt(e.screen_height,10)||0,r.OrStatus=parseInt(e.ori_status,10)||3,
r.Fromid=parseInt(e.fromid,10)||0,r.SessionId=(window.sessionid||"").toString(),
r.AppmsgScene=parseInt(window.source||(window.cgiData?window.cgiData.scene:0),10)||0,
!r.AppmsgScene&&r.Fromid?r.AppmsgScene=r.Fromid:!r.Fromid&&r.AppmsgScene&&(r.Fromid=r.AppmsgScene),
r.AppmsgScene=parseInt(r.AppmsgScene,10)||0,r.Fromid=parseInt(r.Fromid,10)||0,r.TotalRange=parseInt(e.total_range,10)||0,
r.CurrentRange=parseInt(e.current_range,10)||0,r.Duration=parseInt(e.duration,10)||0,
r.RemindTrafficSize=parseInt(e.remind_traffic_size,10)||0,r.TrafficReminderType=parseInt(e.traffic_reminder_type,10)||0,
n.report(12710,r);
}catch(p){}
};
return{
report:s,
getWebviewid:d,
showAd:o,
commReport:p
};
});define("biz_wap/jsapi/leaveReport.js",["biz_wap/jsapi/core.js","biz_common/utils/url/parse.js"],function(e){
"use strict";
function n(e){
var n={};
return"undefined"!=typeof uin&&(n.uin=uin),"undefined"!=typeof key&&(n.key=key),
"undefined"!=typeof pass_ticket&&(n.pass_ticket=pass_ticket),"undefined"!=typeof wxtoken&&(n.wxtoken=wxtoken),
"undefined"!=typeof window.devicetype&&(n.devicetype=window.devicetype),"undefined"!=typeof window.clientversion&&(n.clientversion=window.clientversion),
"undefined"!=typeof appmsg_token?n.appmsg_token=appmsg_token:e.indexOf("advertisement_report")>-1&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=68064_13_1&r="+Math.random()),
n.x5=a?"1":"0",n.f="json",p.join(e,n);
}
function t(e,n){
if(e instanceof Object&&n instanceof Object)for(var t in n)Object.prototype.hasOwnProperty.call(n,t)&&(e[t]=n[t]);
}
function o(e){
"function"==typeof e?s.push(e):data instanceof Object&&c.push(e);
}
function i(e,n){
f[e]||(f[e]=[]),f[e].push(n);
}
var r=e("biz_wap/jsapi/core.js"),p=e("biz_common/utils/url/parse.js"),a=-1!=navigator.userAgent.indexOf("TBS/"),s=[],c=[],f=[];
return r.on("reportOnLeaveForMP",function(){
var e={};
for(var o in f){
e[o]||(e[o]={});
for(var i=0;i<f[o].length;i++){
var r=f[o][i];
"function"==typeof r?t(e[o],r()):p instanceof Object&&t(e[o],r);
}
}
for(var i=0;i<s.length;i++){
var p=s[i]();
p instanceof Object&&c.push(p);
}
for(var i=0;i<c.length;i++)c[i].reportUrl&&(c[i].reportUrl=n(c[i].reportUrl));
return e.data={
requestList:c
},e;
}),{
addReport:o,
addSpecificReport:i
};
});define("biz_wap/utils/hand_up_state.js",["biz_common/dom/event.js"],function(n){
"use strict";
function e(){
if("hidden"in document)return"hidden";
for(var n=["webkit","moz","ms","o"],e=0;e<n.length;e++)return n[e]+"Hidden"in document,
n[e]+"Hidden";
return null;
}
function i(){
var n=e();
return n?document[n]:!1;
}
function t(){
return r;
}
var d=n("biz_common/dom/event.js"),o=e(),r=0,u=0;
if(o){
var m=o.replace(/[H|h]idden/,"")+"visibilitychange";
d.on(document,m,function(){
i()?u=(new Date).getTime():r+=(new Date).getTime()-u;
},!1);
}
return{
getHandUpTime:t,
isHidden:i
};
});define("biz_wap/utils/storage.js",[],function(){
"use strict";
function t(t){
if(!t)throw"require function name.";
this.key=t,this.init();
}
var e="__WXLS__",n=window.localStorage||{
getItem:function(){},
setItem:function(){},
removeItem:function(){},
key:function(){},
length:0
};
return t.getItem=function(t){
return t=e+t,n.getItem(t);
},t.setItem=function(i,r){
i=e+i;
for(var a=3;a--;)try{
n.setItem(i,r);
break;
}catch(o){
t.clear();
}
},t.clear=function(){
var t,i;
for(t=n.length-1;t>=0;t--)i=n.key(t),0==i.indexOf(e)&&n.removeItem(i);
},t.prototype={
constructor:t,
init:function(){
this.check();
},
getData:function(){
var e=t.getItem(this.key)||"{}";
try{
e=JSON.parse(e);
}catch(n){
e={};
}
return e;
},
check:function(){
var e,n,i=this.getData(),r={},a=+new Date;
for(e in i)n=i[e],+n.exp>a&&(r[e]=n);
t.setItem(this.key,JSON.stringify(r));
},
set:function(e,n,i){
var r=this.getData();
r[e]={
val:n,
exp:i||+new Date
},t.setItem(this.key,JSON.stringify(r));
},
get:function(t){
var e=this.getData();
return e=e[t],e?e.val||null:null;
},
remove:function(e){
var n=this.getData();
n[e]&&delete n[e],t.setItem(this.key,JSON.stringify(n));
}
},t;
});define("biz_common/utils/http.js",[],function(){
"use strict";
function t(){
var t=document.getElementsByTagName("html");
if(t&&1==!!t.length){
t=t[0].innerHTML;
var e=t.replace(/[\x00-\xff]/g,""),n=t.replace(/[^\x00-\xff]/g,"");
return 1*n.length+3*e.length+"<!DOCTYPE html><html></html>".length;
}
return 0;
}
return{
htmlSize:t()
};
});define("biz_common/utils/cookie.js",[],function(){
"use strict";
var e={
get:function(e){
if(""==e)return"";
var t=new RegExp(e+"=([^;]*)"),n=document.cookie.match(t);
return n&&n[1]||"";
},
set:function(e,t,n){
var o=new Date;
return o.setDate(o.getDate()+(n||1)),n=o.toGMTString(),document.cookie=e+"="+t+";expires="+n,
!0;
}
};
return e;
});define("appmsg/open_url_with_webview.js",["biz_wap/jsapi/core.js"],function(e){
"use strict";
var r=e("biz_wap/jsapi/core.js"),n=-1!=navigator.userAgent.indexOf("WindowsWechat"),i=function(e,i){
if(n)return location.href=e,!1;
i=i||{};
var o=i.sample||0;
o*=1e3;
var t=window.user_uin||0,s=0!==t&&Math.floor(t/100)%1e3<o;
return s?void r.invoke("openUrlWithExtraWebview",{
url:e,
openType:i.openType||1,
scene:i.scene||"",
bizUsername:i.user_name||""
},function(e){
e&&"openUrlWithExtraWebview:ok"===e.err_msg?i.resolve&&i.resolve():i.reject&&i.reject();
}):void(i.reject&&i.reject());
};
return i;
});define("appmsg/more_read.js",["biz_common/utils/string/html.js","biz_common/tmpl.js","biz_wap/utils/ajax.js","appmsg/more_read_tpl.html.js","biz_wap/utils/openUrl.js","biz_common/dom/event.js","biz_common/utils/monitor.js","common/utils.js"],function(n){
"use strict";
function i(n){
for(var i=c.getInnerHeight(),e=document.documentElement.clientWidth||window.innerWidth,t=document.body.scrollHeight||document.body.offsetHeight,s=document.body.scrollTop||document.documentElement.scrollTop,m=[],d=0;d<l.length;d++){
var w=[l[d].bizuin||window.biz||"",l[d].mid||"",l[d].idx||""].join("_");
m.push(w);
}
m=m.join("#");
var h=r[n.index].getBoundingClientRect(),p="fans_read_cnt="+l[n.index].fans_read_cnt,g={
act:n.action||0,
bizuin:window.biz||"",
msgid:window.mid||"",
idx:window.idx||"",
scene:window.source||"",
sub_scene:window.subscene||"",
get_a8_key_scene:window.ascene||"",
screen_height:i,
screen_width:e,
screen_num:Math.ceil(t/i),
action_screen_num:Math.ceil((h.top+h.height+s)/i),
start_time_ms:_,
action_time_ms:Date.now(),
more_msg:m,
a_bizuin:l[n.index].bizuin||window.biz||"",
a_msgid:l[n.index].mid||"",
a_idx:l[n.index].idx||"",
rank:n.index+1,
tip:p,
session_id:u
};
o({
url:"/mp/appmsgreport?action=more_read",
type:"POST",
data:g,
timeout:2e3,
async:!1,
mayAbort:!0
});
var b=1===n.action?4:5;
a.setSum(110809,b,1).send();
}
function e(){
if(l){
for(var n=0,t=c.getInnerHeight(),o=0;o<r.length;o++)if(r[o].dataset.show)n++;else{
var s=r[o].getBoundingClientRect();
s.top+s.height<t&&(r[o].dataset.show=1,i({
action:1,
index:o
}));
}
n>=r.length&&d.off(window,"scroll",e);
}
}
n("biz_common/utils/string/html.js");
var t=n("biz_common/tmpl.js"),o=n("biz_wap/utils/ajax.js"),s=n("appmsg/more_read_tpl.html.js"),m=n("biz_wap/utils/openUrl.js"),d=n("biz_common/dom/event.js"),a=n("biz_common/utils/monitor.js"),c=n("common/utils.js"),l=null,r=null,_=Date.now(),u=""+_+"_"+Math.random().toString(36).substring(2);
return d.on(window,"scroll",e),function(n,e){
l=e,n.innerHTML=t.tmpl(s,{
list:l
}),r=n.getElementsByClassName("more_read_link");
for(var o=0;o<r.length;o++)d.on(r[o],"click",function(n){
return function(){
window.__second_open__?m.openUrlWithExtraWebview(l[n].link.htmlDecode()):window.location.href=l[n].link.htmlDecode(),
i({
action:2,
index:n
});
};
}(o));
n.style.display="";
};
});var _extends=Object.assign||function(e){
for(var t=1;t<arguments.length;t++){
var n=arguments[t];
for(var o in n)Object.prototype.hasOwnProperty.call(n,o)&&(e[o]=n[o]);
}
return e;
};
define("appmsg/comment.js",["biz_common/utils/string/html.js","biz_common/dom/class.js","appmsg/cmt_tpl.html.js","biz_common/utils/wxgspeedsdk.js","appmsg/comment_report.js","biz_wap/utils/device.js","appmsg/retry_ajax.js","biz_common/dom/offset.js","biz_common/utils/url/parse.js","biz_wap/jsapi/core.js","common/utils.js","appmsg/emotion/selection.js","appmsg/i18n.js","biz_common/dom/event.js","biz_wap/utils/ajax.js","biz_common/tmpl.js","biz_wap/utils/fakehash.js","appmsg/log.js","appmsg/my_comment_tpl.html.js","appmsg/emotion/dom.js","pages/utils.js","biz_wap/utils/mmversion.js","common/comm_report.js","biz_wap/utils/position.js","appmsg/emotion/emotion_pc.js","appmsg/emotion/emotion.js","appmsg/comment_tpl.html.js","appmsg/comment_pc_tpl.html.js","appmsg/friend_comment_tpl.html.js"],function(e,t,n,o){
"use strict";
function i(e){
var t=document.getElementById(e);
t.parentNode.removeChild(t);
}
function m(e,t){
e&&(e.style.display=t||"block");
}
function d(e){
e&&(e.style.display="none");
}
function s(){
St.mylist.children.length?(m(St.mylist.parentNode),Yt||G.removeClass(document.body,Qt)):(d(St.mylist.parentNode),
Yt||G.addClass(document.body,Qt));
}
function a(e){
St.el_alertContent.innerHTML=e,St.el_alertPanel.style.display="";
}
function c(){
Yt?(G.removeClass(document.getElementById("js_success_panel_pc"),"weui-transition_opacity-hide"),
setTimeout(function(){
G.addClass(document.getElementById("js_success_panel_pc"),"weui-transition_opacity-hide");
},750)):(setTimeout(function(){
m(St.toast);
},750),setTimeout(function(){
d(St.toast);
},1500));
}
function l(e){
return e.toString().replace(/^\s+|\s+$/g,"");
}
function r(e,t){
if(!(Math.random()<.999)){
var n=9;
"https:"===window.location.protocol&&(n=18),V.saveSpeeds({
uin:window.uin,
pid:n,
speeds:[{
sid:29,
time:e
},{
sid:30,
time:t
}]
}),V.send();
}
}
function _(e){
var t=arguments.length<=1||void 0===arguments[1]?"":arguments[1];
if("undefined"!=typeof e){
var n=new Image,o=Math.random();
n.src=ht.idkey?"/mp/jsmonitor?idkey="+ht.idkey+"_"+e+"_1&t="+o:"/mp/jsreport?key="+e+"&content="+t+"&r="+o;
}
}
function p(){
vt||(vt=!0,new Q({
comment_id:kt,
appmsgid:window.appmsgid,
idx:window.idx,
item_show_type:window.item_show_type||0,
biz:window.biz
}));
}
function u(){
try{
var e=St.loading.getBoundingClientRect(),t=Math.random()<1;
e.top<et.getInnerHeight()&&xt&&t&&((new Image).src="/mp/jsmonitor?idkey=28307_45_1&lc=1&log0",
ot.off(window,"scroll",u));
}catch(n){
console.error(n);
}
}
function g(){
var e=St.showAll,t=et.getScrollTop(),n=pt.getY(e,"js_article");
return 0===e.clientHeight?!1:(e.clientHeight+n>=t+e.clientHeight/2&&e.clientHeight+n<=t+e.clientHeight/2+et.getInnerHeight()&&(_t.report(18832,_extends({
Actiontype:1,
Type:3,
Bizuin:0,
Msgid:0,
Itemidx:0,
Sendtimestamp:0,
Pos:0
},gt)),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_26_1&r="+Math.random(),
ot.off(window,"scroll",g)),!0);
}
function f(e){
var t=(new Date).getTime(),n=new Date;
n.setDate(n.getDate()+1),n.setHours(0),n.setMinutes(0),n.setSeconds(0),n=n.getTime();
var o=t/1e3-e,i=n/1e3-e,m=new Date(n).getFullYear(),d=new Date(1e3*e);
return 3600>o?Math.ceil(o/60)+"分钟前":86400>i?Math.floor(o/60/60)+"小时前":172800>i?"昨天":604800>i?Math.floor(i/24/60/60)+"天前":d.getFullYear()===m?d.getMonth()+1+"月"+d.getDate()+"日":d.getFullYear()+"年"+(d.getMonth()+1)+"月"+d.getDate()+"日";
}
function w(e){
ct.each(e.querySelectorAll("div.discuss_message_content"),function(e){
e.innerHTML=en.encode(e.innerHTML);
});
}
function y(e,t,n){
var o=void 0,i=void 0,m="",d="",s=document.createElement("div");
"elected"===n?d=0:"friend"===n&&(d=1),Nt={};
for(var a=0;a<e.length;a++){
if(i=e[a],i.time=f(i.create_time),i.status="",i.logo_url=i.logo_url||tn,i.logo_url=-1!==i.logo_url.indexOf("wx.qlogo.cn")?i.logo_url.replace(/\/132$/,"/96"):i.logo_url,
i.content=i.content.htmlDecodeLite().htmlEncodeLite(),i.nick_name=i.nick_name.htmlDecodeLite().htmlEncodeLite(),
i.like_num_format=parseInt(i.like_num,10)>=1e4?(i.like_num/1e4).toFixed(1)+"万":i.like_num,
"en"===window.LANG&&(i.like_num_format=nt.dealLikeReadShow_en(i.like_num)),i.is_from_friend="friend"===n?0:i.is_from_friend||0,
i.is_from_me="mine"===n?1:i.is_from_me||0,i.reply=i.reply||{
reply_list:[]
},i.is_mine=!n,i.is_elected="elected"===n||"friend"===n?1:i.is_elected,i.is_top="friend"===n?0:i.is_top,
i.report_elected=i.is_elected||0,i.report_friend=i.is_from_friend||0,i.scene=d,i.reply.reply_list.length>0){
var c=i.reply.reply_list[0];
c.time=f(c.create_time),c.content=(c.content||"").htmlEncodeLite(),c.reply_like_status=c.reply_like_status||0,
c.reply_like_num=c.reply_like_num||0,c.reply_like_num_format=parseInt(c.reply_like_num,10)>=1e4?(c.reply_like_num/1e4).toFixed(1)+"万":c.reply_like_num,
"en"===window.LANG&&(c.reply_like_num_format=nt.dealLikeReadShow_en(c.reply_like_num));
}
i.new_appmsg=window.new_appmsg,m+=mt.tmpl(Y,i);
try{
var l=i.nick_name+i.content,r=!1,p=ht.repeatContentID;
Nt[l]&&(r=!0,p=ht.repeatContent),Dt.indexOf(i.content_id)>-1&&(r=!0,p=ht.repeatContentID),
Dt.push(i.content_id),Nt[l]=!0,r&&_(p,encodeURIComponent(JSON.stringify({
comment_id:kt,
content_id:i.content_id,
offset:Et,
length:e.length,
url:Gt
})));
}catch(u){
console.error(u);
}
}
for(s.innerHTML=m,w(s);s.children.item(0);)o=s.children.item(0),t.appendChild(o);
}
function h(e){
var t=void 0,n=void 0,o=Date.now(),i=e.resp,s=e.loadTime,a=e.forceRefresh,c=document.createDocumentFragment(),l=document.createDocumentFragment();
if(It=i.only_fans_can_comment,_(ht.handleList,encodeURIComponent(JSON.stringify({
comment_id:kt,
offset:Et,
url:Gt
}))),1!==i.enabled?(Xt&&(Xt.style.display="none"),Zt&&d(Zt),i.elected_comment=[],
i.friend_comment=[],i.elected_comment_total_cnt=0,i.friend_comment_total_cnt=0):(Xt&&(Xt.style.display="block"),
Zt&&m(Zt)),0===Et){
if(Mt=i.logo_url,At=i.nick_name,a&&(Dt=[]),t=i.elected_comment,t&&t.length){
if(y(t,c,"elected"),a&&(St.list.innerHTML=""),St.list.appendChild(c),m(St.main),
qt&&0===Ut?(document.getElementById("js_cmt_nofans1").innerHTML="作者已设置关注3天后才可留言",
m(document.getElementById("js_cmt_nofans1"),"block")):It&&0===i.is_fans?(document.getElementById("js_cmt_nofans1").innerHTML="作者已设置关注后才可以留言",
m(document.getElementById("js_cmt_nofans1"),"block")):ut&&(Yt?(m(St.commentPC),m(St.inputPC)):m(St.addCmtBtn1)),
i.elected_comment_total_cnt<=10&&(m(document.getElementById("js_cmt_statement")),
m(document.getElementById("js_cmt_qa"))),!Bt&&"5"===window.item_show_type){
var u=Date.now()-window.logs.pagetime.page_begin;
Bt=!0,Math.random()<.1&&(V.saveSpeeds({
uin:window.uin,
pid:675,
speeds:[{
sid:27,
time:u
}]
}),V.send());
}
}else d(St.main),qt&&0===Ut?(document.getElementById("js_cmt_nofans2_inner").innerHTML="作者已设置关注3天后才可留言",
m(document.getElementById("js_cmt_nofans2"),"block")):It&&0===i.is_fans?(document.getElementById("js_cmt_nofans2_inner").innerHTML="作者已设置关注后才可以留言",
m(document.getElementById("js_cmt_nofans2"),"block")):ut&&(Yt?(m(St.commentPC),m(St.inputPC)):m(St.addCmtBtn2));
n=i.friend_comment,y(n,l,"friend"),n&&0===n.length&&d(Zt),a&&(St.fdlist.innerHTML=""),
St.fdlist&&St.fdlist.appendChild(l),n&&n.length?(m(St.fdmain),(!It||It&&1===i.is_fans)&&(Yt||(d(St.addCmtBtn1),
d(St.addCmtBtn2),ut&&m(St.addCmtBtn3)))):d(St.fdmain);
var g=document.getElementById("js_cmt_area");
location.href.indexOf("scrolltodown")>-1&&g&&g.offsetTop&&window.scrollTo(0,g.offsetTop-25);
}else t=i.elected_comment,t&&t.length&&(y(t,c,"elected"),St.list.appendChild(c));
0===i.elected_comment_total_cnt?(Et=-1,d(document.getElementById("js_cmt_loading")),
d(document.getElementById("js_cmt_statement")),d(document.getElementById("js_cmt_qa"))):Et+Wt>=i.elected_comment_total_cnt?(Et=-1,
d(document.getElementById("js_cmt_loading")),m(document.getElementById("js_cmt_statement")),
m(document.getElementById("js_cmt_qa"))):Et+=i.elected_comment.length;
var f=5;
if(window.user_uin%2===0&&(f=8),t.length>f&&window.has_related_article){
var w=0;
m(St.showAll),d(document.getElementById("js_cmt_statement"));
for(var h=St.list.querySelectorAll("li.js_comment_item"),j=0;f>j;j++){
var C=window.getComputedStyle(h[j]);
w+=h[j].getBoundingClientRect().height+parseFloat(C.paddingTop)+parseFloat(C.paddingBottom)+parseFloat(C.borderTopWidth)+parseFloat(C.borderBottomWidth)+parseFloat(C.marginTop)+parseFloat(C.marginBottom);
}
St.listContainer.style.height=w+"px",St.showAllWording.innerText="查看更多%s条留言".replace("%s",t.length-f),
(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_25_1&r="+Math.random();
}
p(),lt.setTwoTabHeight("js_comment_content"),s&&r(s,Date.now()-o);
}
function j(e){
if(kt=window.comment_id,0!==Number(kt)){
var t=e.forceRefresh,n=e.cb;
t=t===!0,t&&(Et=0);
var o=et.getScrollTop(),i=document.documentElement.scrollHeight;
if(!(xt||-1===Et||Et>0&&i-o-et.getInnerHeight()>500)){
if("number"==typeof Ct&&0===Ct&&!t)return void h({
resp:{
enabled:1,
elected_comment:[],
friend_comment:[],
elected_comment_total_cnt:0,
my_comment:[],
only_fans_can_comment:It,
is_fans:jt,
logo_url:Mt,
nick_name:At
}
});
var s=$.join("/mp/appmsg_comment",{
action:"getcomment",
scene:ht.scene,
appmsgid:window.appmsgid,
idx:window.idx,
comment_id:kt,
offset:Et,
limit:Wt,
send_time:window.send_time
},!0),a=+new Date;
xt=!0,d(St.tips),m(St.loading);
try{
Ht++,t&&(Lt=[]),Ht>1&&!t&&_(ht.moreList,encodeURIComponent(s)),Lt.indexOf(s)>-1&&_(ht.repeatList,encodeURIComponent(s)),
Lt.push(s);
}catch(c){
console.error(c);
}
Kt&&console.info("[图文评论] 开始请求评论数据:",s),st("[Appmsg comment] start get comment data, url:"+s),
it({
url:s,
dataType:"json",
success:function(e){
var o=e.base_resp&&e.base_resp.ret;
0===o?n&&n({
resp:e,
forceRefresh:t,
loadTime:Date.now()-a
}):_(ht.errList,"type:resperr;url:"+encodeURIComponent(s)+";ret="+o),st("[Appmsg comment] get comment success");
},
error:function(){
_(ht.errList,"type:ajaxerr;url:"+encodeURIComponent(s)),st("[Appmsg comment] get comment ajax error");
},
complete:function(){
xt=!1,d(St.loading),ot.off(window,"scroll",u);
}
});
}
}
}
function C(){
St.list.children.length?St.fdlist.children.length?(ut&&m(St.addCmtBtn3),d(St.addCmtBtn1),
d(St.addCmtBtn2),d(St.addCmtBtn4)):(ut&&m(St.addCmtBtn1),d(St.addCmtBtn2),d(St.addCmtBtn3),
d(St.addCmtBtn4)):St.fdlist.children.length?(ut&&m(St.addCmtBtn3),d(St.addCmtBtn4),
d(St.addCmtBtn1),d(St.addCmtBtn2)):(ut&&m(St.addCmtBtn2),d(St.addCmtBtn3),d(St.addCmtBtn1),
d(St.addCmtBtn4)),Yt&&(d(St.addCmtBtn1),d(St.addCmtBtn2),d(St.addCmtBtn3));
}
function b(e,t){
var n=document.createDocumentFragment();
c(),y([{
content:t,
nick_name:At,
create_time:Date.now()/1e3|0,
is_elected:0,
logo_url:Mt,
like_status:0,
like_num_format:0,
like_num:0,
is_from_friend:0,
is_from_me:1,
my_id:e.my_id,
content_id:e.content_id
}],n,"mine"),St.mylist.insertBefore(n,St.mylist.firstChild),s(),Yt?(St.input.innerHTML="",
St.inputHolder.style.display=""):St.input.value="",C();
}
function v(){
ct.log("tag1");
var e=void 0,t=$.join("/mp/appmsg_comment",{
action:"addcomment",
scene:ht.scene,
appmsgid:window.appmsgid,
idx:window.idx,
comment_id:kt,
sn:window.sn
},!0);
if(e=Yt?l(zt).replace(/<br\/>/g,"").replace(/\n/g,"")||"":l(St.input.value),ct.log("tag2"),
!G.hasClass(St.submit,"btn_disabled")&&St.submit.disabled!==!0){
if(ct.log("tag3"),e.length<1)return void a("留言不能为空");
if(ct.log("tag4"),e.length>600)return void a("字数不能多于600个");
Yt&&(e=zt),ct.log("tag5"),Yt?St.submit.disabled=!0:G.addClass(St.submit,"btn_disabled"),
ct.log("tag6");
var n=document.getElementById("activity-name");
ct.log("tag7"),bt!==e&&(Ft=Date.now()),it({
url:t,
data:{
content:e,
title:n&&l(n.innerText),
head_img:Mt,
nickname:At,
client_id:Ft
},
type:"POST",
dataType:"json",
success:function(n){
switch(ct.log("tag8"),Yt||en.hidePannel(),+n.ret){
case 0:
b(n,e);
break;

case-6:
a("你留言的太频繁了，休息一下吧");
break;

case-7:
a("你还未关注该公众号，不能参与留言");
break;

case-10:
a("字数不能多于600个");
break;

case-15:
a("留言已关闭");
break;

default:
bt=e,a("系统错误，请重试");
}
0!==Number(n.ret)&&_(ht.addCommentErr,"type:resperr;url:"+encodeURIComponent(t)+";ret="+n.ret);
},
error:function(e){
ct.log("shit;"+e.status+";"+e.statusText),_(ht.addCommentErr,"type:ajaxerr;url:"+encodeURIComponent(t));
},
complete:function(){
""!==St.input.value&&G.removeClass(St.submit,"btn_disabled");
}
});
}
}
function I(e){
return e.filter(function(e){
return!e.is_elected&&1!==e.is_elected;
});
}
function B(){
var e=document.getElementById("js_mycmt_loading"),t=$.join("/mp/appmsg_comment",{
action:"getmycomment",
scene:ht.scene,
appmsgid:window.appmsgid,
idx:window.idx,
comment_id:kt
},!0);
s(),0===Rt&&(Rt=1,m(e),it({
url:t,
dataType:"json",
success:function(e){
var n=e.base_resp&&e.base_resp.ret;
if(0===n){
var o=e.my_comment,i=document.createDocumentFragment();
o&&o.length&&(Yt&&(m(St.myareaPC),m(St.mylist),o=I(o)),y(o,i,"mine"),St.mylist.appendChild(i)),
Rt=2;
}else Rt=0,_(ht.errComment,"type:resperr;url:"+encodeURIComponent(t)+";ret="+n);
},
error:function(){
Rt=0,_(ht.errComment,"type:ajaxerr;url:"+encodeURIComponent(t));
},
complete:function(){
d(e),s();
}
}));
}
function k(e){
Tt=et.getScrollTop(),d(St.article),m(St.mine),St.deletePanel=document.getElementById("js_delete_panel_mobile"),
St.deleteConfirm=document.getElementById("js_delete_confirm_mobile"),St.deleteCancel=document.getElementById("js_delete_cancel_mobile"),
window.__second_open__&&J.os.ios&&m(St.fakebar),window.scrollTo(0,0),B(),e||ct.later(function(){
St.input.focus();
});
}
function E(){
"1"===$.getQuery("js_my_comment")&&k(!0);
}
function T(){
return rt.isWechat?J.os.ipad?!1:rt.isInMiniProgram?!1:rt.isIOS&&rt.gtVersion("7.0.8")?!0:rt.isAndroid&&rt.gtVersion("7.0.8")?!0:et.isNativePage()&&(rt.isIOS||rt.isAndroid)?!0:!1:!1;
}
function x(){
var e=document.getElementById("activity-name");
return T()?(K.invoke("handleMPPageAction",{
action:"writeComment",
title:e&&l(e.innerText),
comment_id:kt,
style:mn?"black":"white"
}),!0):!1;
}
function M(){
d(St.mine),m(St.article),St.deletePanel=document.getElementById("js_delete_panel"),
St.deleteConfirm=document.getElementById("js_delete_confirm"),St.deleteCancel=document.getElementById("js_delete_cancel"),
window.scrollTo(0,Tt),St.input.blur(),G.removeClass(document.body,Vt),G.removeClass(document.body,Qt),
et.isNativePage()||on(mn||Ot?"#232323":"#ffffff");
}
function P(e){
var t=G.hasClass(e,"praised"),n=e.querySelector(".praise_num"),o=parseInt(n.getAttribute("data-num")||0,10),i=n.getAttribute("data-like");
t===("1"===i)&&(t?o--:o++),"en"===window.LANG?n.innerHTML=nt.dealLikeReadShow_en(o):-1===n.innerHTML.indexOf("万")&&(n.innerHTML=o),
t?(G.removeClass(e,"praised"),e.dataset.status=0):(G.addClass(e,"praised"),e.dataset.status=1);
}
function H(e){
var t=e.delegatedTarget||e.srcElement,n=null;
if(G.hasClass(t,"js_comment_praise")&&(n=t),n){
for(var o=parseInt(n.dataset.status,10),i=0===o?1:0,m=n.dataset.contentId,d=n.dataset.scene,s=document.querySelectorAll('.js_comment_praise[data-content-id="'+m+'"]'),a=0;a<s.length;a++)P(s[a]);
X({
url:"/mp/appmsg_comment?action=likecomment",
type:"POST",
data:{
like:i,
appmsgid:window.appmsgid,
comment_id:kt,
content_id:m,
item_show_type:window.item_show_type||0,
scene:d
}
});
}
}
function L(e){
for(var t=e.delegatedTarget,n=parseInt(t.dataset.status,10),o=n?0:1,i=t.dataset.contentId,m=t.dataset.replyId,d=t.dataset.scene,s=document.querySelectorAll('.js_reply_praise[data-content-id="'+i+'"]'),a=0;a<s.length;a++)P(s[a]);
it({
url:"/mp/appmsg_comment?action=like_author_reply",
type:"post",
data:{
comment_id:kt,
content_id:i,
reply_id:m,
like:o,
scene:d,
item_show_type:window.item_show_type||0
}
});
}
function S(e,t){
e.parentNode.removeChild(e),G.addClass(St.deletePanel,"weui-transition_opacity-hide");
for(var n=document.querySelectorAll(".cid"+t),o=0;o<n.length;o++)n[o].parentNode.removeChild(n[o]);
St.list.children.length?St.fdlist.children.length||d(St.fdmain):(d(St.main),d(document.getElementById("js_cmt_statement")),
d(document.getElementById("js_cmt_qa")),St.fdlist.children.length||d(St.fdmain)),
s(),C();
}
function D(e){
var t=void 0,n=e.delegatedTarget,i=n.getAttribute("data-my-id"),m=$.join("/mp/appmsg_comment",{
action:"delete",
scene:ht.scene,
appmsgid:window.appmsgid,
my_id:i,
comment_id:kt
},!0);
G.removeClass(St.deletePanel,"weui-transition_opacity-hide"),ot.on(St.deleteConfirm,"click",function(){
t!==i&&(t=i,it({
url:m,
dataType:"json",
success:function(e){
var t=n;
if(0===e.ret){
for(;t&&(t.nodeType!==t.ELEMENT_NODE||"li"!==t.tagName.toLowerCase());)t=t.parentNode;
t&&S(t,i);
}else o("删除失败，请重试");
},
error:function(){
o("网络错误，请重试");
}
}));
}),ot.on(St.deleteCancel,"click",function(){
t!==i&&(t=i,G.addClass(St.deletePanel,"weui-transition_opacity-hide"));
});
}
function z(e){
e&&e.preventDefault(),M(),d(St.fakebar);
}
function A(e,t){
return x()?void _t.report(19048,_extends({
EventType:1,
IsFans:jt,
CommentPageType:2
},yt)):(et.isNativePage()||(G.addClass(document.body,Vt),on("5"===window.item_show_type||Ot?"#191919":"#ffffff")),
t?(Kt&&console.log("FakeHash on comment"),void k()):(e.preventDefault(),window.__second_open__&&J.os.ios?k():(Kt&&console.log("push comment"),
dt.push("comment")),void _t.report(19048,_extends({
EventType:1,
IsFans:jt,
CommentPageType:1
},yt))));
}
function R(e){
window.scrollTo(0,window.scrollY+e.getBoundingClientRect().height);
}
function N(e){
return e.getBoundingClientRect().top+e.getBoundingClientRect().height>=et.getInnerHeight()?!0:!1;
}
function F(){
dt.on("comment",function(){
A(null,!0);
}),dt.on("article",function(){
Kt&&console.log("FakeHash on article"),M();
}),dt.on(function(e){
"comment"===e&&M();
});
}
function O(){
ot.on(St.input,"input",function(e){
if(Yt){
var t=St.input.innerHTML;
""===t||"<br>"===t?(St.inputHolder.style.display="",St.input.innerHTML=""):St.inputHolder.style.display="none";
}
var n=l(St.input.value||St.input.innerHTML);
n.length<1?G.addClass(St.submit,"btn_disabled"):G.removeClass(St.submit,"btn_disabled"),
J.os.ios&&e.data&&nn.indexOf(e.data)>-1&&(Pt=!0);
}),ot.on(St.input,"click",function(){
J.os.ios&&Pt&&(St.input.blur(),St.input.focus(),Pt=!1);
}),ot.on(St.el_alertConfirm,"click",function(){
St.el_alertPanel.style.display="none";
}),Yt&&ot.on(St.input,"click",function(){
d(document.getElementById("js_emotion_panel_pc"));
}),ot.on(St.list,"click",".js_comment_praise",H),ot.on(St.mylist,"click",".js_comment_praise",H),
ot.on(St.fdlist,"click",".js_comment_praise",H),ot.on(St.list,"click",".js_reply_praise",L),
ot.on(St.fdlist,"click",".js_reply_praise",L),ot.on(St.list,"click",".js_del",D),
ot.on(St.mylist,"click",".js_del",D),ot.on(St.fdlist,"click",".js_del",D),et.listenMpPageAction(function(e){
"deleteComment"===e.action&&S(document.getElementById("cid"+e.personal_comment_id),e.personal_comment_id);
}),ot.on(St.list,"click",".js_del",function(e){
e.preventDefault();
}),ot.on(St.mylist,"click",".js_del",function(e){
e.preventDefault();
}),ot.on(St.fdlist,"click",".js_del",function(e){
e.preventDefault();
}),ot.on(St.submit,"click",v),ot.on(St.submit,"click",function(e){
e.preventDefault();
}),St.goback&&(ot.on(St.goback,"click",z),ot.on(St.goback,"click",z)),window.__second_open__&&J.os.ios&&!function(){
ot.on(St.input,"click",function(){
d(St.fakebar);
}),ot.on(St.input,"blur",function(){
"none"!==St.mine.style.display&&m(St.fakebar);
});
var e=null,t=null;
ot.on(window,"orientationchange",function(){
"none"!==St.fakebar.style.display&&(clearTimeout(e),e=setTimeout(function(){
window.innerWidth!==parseFloat(getComputedStyle(St.fakebar).width)&&(clearTimeout(t),
St.mine.style.height=et.getInnerHeight()+"px",window.scrollBy&&window.scrollBy(0,1),
t=setTimeout(function(){
window.scrollBy&&window.scrollBy(0,-1),St.mine.style.height="";
},100));
},50));
});
}(),ot.on(window,"scroll",u),window.hasRelatedArticleInfo&&ot.on(window,"scroll",g),
ot.on(document.getElementById("js_cmt_write1"),"click",function(e){
A(e);
}),ot.on(document.getElementById("js_cmt_write2"),"click",function(e){
A(e);
}),ot.on(document.getElementById("js_cmt_write3"),"click",function(e){
A(e);
}),ot.on(document.getElementById("js_cmt_write4"),"click",function(e){
A(e);
}),ot.on(St.inputPC,"click",function(){
d(St.inputPC),m(St.containerPC),N(St.containerPC)&&R(St.containerPC),St.input.focus();
}),ot.bindVisibilityChangeEvt(function(e){
e&&et.getScrollTop()<Z.getOffset(St.cmtContainer).offsetTop-et.getInnerHeight()&&j({
forceRefresh:!0,
cb:h
});
}),ot.on(St.showAllWording,"tap",function(e){
e.preventDefault(),d(St.showAll),m(document.getElementById("js_cmt_statement")),
St.listContainer.style.height=St.list.clientHeight+"px",_t.report(18832,_extends({
Actiontype:2,
Type:3,
Bizuin:0,
Msgid:0,
Itemidx:0,
Sendtimestamp:0,
Pos:0
},gt)),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_27_1&r="+Math.random();
});
}
function q(){
function e(){
var e=document.createElement("div"),t="";
e.innerHTML=St.input.innerHTML;
for(var n=e.childNodes.length-1;n>=0;n--){
var o=e.childNodes[n];
switch(o.nodeType){
case 1:
if("BR"!==o.nodeName.toUpperCase()){
var i=void 0,m=!1;
if(i="IMG"===o.nodeName.toUpperCase()?o:"",i||(i=o.textContent||o.innerText||"",
m=!0),i){
var d=m?document.createTextNode(i):i;
e.replaceChild(d,o);
}else e.removeChild(o);
}
break;

case 3:
break;

default:
e.removeChild(o);
}
}
return t=e.innerHTML;
}
function t(){
g=tt.getRange();
}
function n(){
if(g){
var e=tt.getSelection();
if(e.addRange)e.removeAllRanges(),e.addRange(g);else{
var t=tt.getRange();
t.setEndPoint&&(t.setEndPoint("EndToEnd",g),t.setEndPoint("StartToStart",g)),t.select();
}
}
}
function o(){
St.input.focus(),St.input.scrollTop=St.input.scrollHeight,n();
}
function i(){
var e=l(zt).replace(/<br\/>/g,"").replace(/\n/g,"").length;
y.innerText=e,e>600?(w.style.display="",G.addClass(w,"comment_primary_counter_warn"),
St.submit.disabled=!0):1>e?(w.style.display="none",G.removeClass(w,"comment_primary_counter_warn"),
St.submit.disabled=!0):(w.style.display="none",G.removeClass(w,"comment_primary_counter_warn"),
St.submit.disabled=!1);
}
function s(e,t){
var n=["&#96;","`","&#39;","'","&quot;",'"',"&nbsp;"," ","&gt;",">","&lt;","<","&yen;","¥","&amp;","&"],o=["&","&amp;","¥","&yen;","<","&lt;",">","&gt;"," ","&nbsp;",'"',"&quot;","'","&#39;","`","&#96;"],i=void 0;
i=t?o:n;
for(var m=0;m<i.length;m+=2)e=e.replace(new RegExp(i[m],"g"),i[m+1]);
return e;
}
function a(){
document.execCommand("AutoUrlDetect",!1,!1);
var t=e();
t=s(t),zt=en.textFilter(t),i();
}
function c(e){
o();
var n=tt.getRange();
if(n){
if(n.createContextualFragment){
e+='<img style="width:1px;height:1px;"></img>';
var i=n.createContextualFragment(e),m=i.lastChild,d=tt.getSelection();
n.deleteContents(),n.insertNode(i),n.setStartBefore(m),n.setEndAfter(m),d.removeAllRanges(),
d.addRange(n),document.execCommand("Delete",!1,null);
}else n.pasteHTML&&e&&(n.pasteHTML(e),n.select(),n.collapse&&n.collapse(!1));
t(),a();
}
}
function r(e){
var t=e.currentTarget,n=t.getAttribute("data-index"),o=f[n].name,i='<img src="/mpres/zh_CN/htmledition/comm_htmledition/images/pic/common/pic_blank.gif"\n      class="icon_emotion_single '+o+'" alt="mo-'+f[n].title+'"></img>';
c(i),en.emotionPanelMove();
}
function _(){
for(var e=St.input,t=void 0,n=e.childNodes.length-1;n>=0;n--){
var o=e.childNodes[n];
switch(o.nodeType){
case 1:
if("BR"!==o.nodeName.toUpperCase()){
var i=void 0,m=!1;
if(i="IMG"===o.nodeName.toUpperCase()?o:"",i||(i=o.textContent||o.innerText||"",
m=!0),i){
var d=m?document.createTextNode(i):i;
t||(t=d),e.replaceChild(d,o);
}else e.removeChild(o);
}
break;

case 3:
break;

default:
e.removeChild(o);
}
}
tt.setCursorToEnd(t);
}
function p(e,t){
for(;void 0!==e&&null!==e&&null!==e.tagName&&"BODY"!==e.tagName.toUpperCase();){
if(e===t)return!0;
e=e.parentNode;
}
return!1;
}
var u=void 0,g=tt.getRange(),f=en.edata,w=document.getElementById("js_length_notice_pc"),y=document.getElementById("js_word_length_pc");
J.os.Mac&&(window.onblur=function(){
St.input&&"none"!==St.input.display&&""!==St.input.innerHTML&&St.input.blur();
}),ot.on(St.input,"keyup",function(){
t(),a();
}),ot.on(St.input,"keydown",function(e){
return 13===e.keyCode?(c("<br/>"),t(),!1):void 0;
}),ot.on(St.input,"mouseup",function(){
t(),a();
}),ot.on(St.input,"paste",function(){
u&&clearTimeout(u),u=setTimeout(function(){
return _(),t(),a(),!1;
},10);
}),ot.on(document,"click",function(e){
var t=e.srcElement||e.delegatedTarget,n=document.getElementById("js_emotion_panel_pc");
if(!p(t,St.addbtnPC)&&"none"!==St.containerPC.style.display){
var o=St.input.innerHTML;
""===l(o)&&(d(St.containerPC),m(St.inputPC),d(n));
}
p(t,n)||p(t,St.emotionSwitchPC)||"none"===n.style.display||d(n);
},!1),ct("li.js_emotion_item").on("click",r);
}
function U(t){
if(It=t.only_fans_can_comment,At=t.nick_name,jt=t.is_fans,Mt=t.logo_url,Ct=t.comment_count,
qt=t.only_fans_days_can_comment,Ut=t.is_fans_days,window._has_comment=!0,!Jt||0===Number(kt))return void(window._has_comment=!1);
if(Xt){
var n=e("appmsg/comment_tpl.html.js"),o=e("appmsg/comment_pc_tpl.html.js");
Xt.innerHTML=mt.tmpl(n,{
new_appmsg:window.new_appmsg
}),$t.insertAdjacentHTML("afterbegin",mt.tmpl(o,{
new_appmsg:window.new_appmsg
}));
}
if(Zt){
var m=e("appmsg/friend_comment_tpl.html.js");
Zt.innerHTML=mt.tmpl(m,{
new_appmsg:window.new_appmsg
});
}
var d=document.createElement("div");
d.innerHTML=mt.tmpl(at,{
new_appmsg:window.new_appmsg,
isIos:J.os.ios
}),document.body.appendChild(d),Yt?(i("js_cmt_mine"),document.getElementById("js_avatar_pc").src=Mt,
G.addClass(document.body,"pages_skin_pc")):i("js_cmt_addbtn_pc"),St={
article:document.getElementById("js_article"),
mine:document.getElementById("js_cmt_mine"),
main:document.getElementById("js_cmt_main"),
input:document.getElementById("js_cmt_input"),
submit:document.getElementById("js_cmt_submit"),
goback:document.getElementById("js_cmt_goback"),
addbtn:document.getElementById("js_cmt_addbtn"),
list:document.getElementById("js_cmt_list"),
mylist:document.getElementById(Yt?"js_cmt_mylist_pc":"js_cmt_mylist"),
morelist:document.getElementById("js_cmt_morelist"),
toast:document.getElementById("js_cmt_toast"),
tips:document.getElementById("js_cmt_tips"),
loading:document.getElementById("js_cmt_loading"),
fdmain:document.getElementById("js_friend_cmt_main"),
fdlist:document.getElementById("js_friend_cmt_list"),
fdlisthide:document.getElementById("js_friend_cmt_list_hide"),
morefdlist:document.getElementById("js_more_friend_cmt_area"),
morefd:document.getElementById("js_more_friend_cmt"),
fakebar:document.getElementById("js_fake_bar"),
showAll:document.getElementById("js_cmt_show_all"),
showAllWording:document.getElementById("js_cmt_show_all_wording"),
listContainer:document.getElementById("js_cmt_list_container"),
cmtContainer:document.getElementById("js_cmt_container"),
inputPC:document.getElementById("js_cmt_input_pc"),
containerPC:document.getElementById("js_cmt_container_pc"),
commentPC:document.getElementById("js_comment_pc"),
addbtnPC:document.getElementById("js_cmt_addbtn_pc"),
myareaPC:document.getElementById("js_cmt_myarea_pc"),
emotionSwitchPC:document.getElementById("js_emotion_wrp_pc"),
deletePanel:document.getElementById("js_delete_panel"),
deleteConfirm:document.getElementById("js_delete_confirm"),
deleteCancel:document.getElementById("js_delete_cancel"),
inputHolder:document.getElementById("js_cmt_input_holder"),
el_alertPanel:document.getElementById("js_alert_panel"),
el_alertContent:document.getElementById("js_alert_content"),
el_alertConfirm:document.getElementById("js_alert_confirm"),
addCmtBtn1:document.getElementById("js_cmt_addbtn1"),
addCmtBtn2:document.getElementById("js_cmt_addbtn2"),
addCmtBtn3:document.getElementById("js_cmt_addbtn3"),
addCmtBtn4:document.getElementById("js_cmt_addbtn4")
},window.__second_open__&&J.os.ios&&(St.mine.style.marginBottom=getComputedStyle(St.fakebar).height),
!t.notAutoGetComment&&j({
forceRefresh:!0,
cb:h
}),E(),Yt&&B(),en.init(),O(),Yt&&q();
}
function W(){
F();
}
e("biz_common/utils/string/html.js");
var G=e("biz_common/dom/class.js"),Y=e("appmsg/cmt_tpl.html.js"),V=e("biz_common/utils/wxgspeedsdk.js"),Q=e("appmsg/comment_report.js"),J=e("biz_wap/utils/device.js"),X=e("appmsg/retry_ajax.js"),Z=e("biz_common/dom/offset.js"),$=e("biz_common/utils/url/parse.js"),K=e("biz_wap/jsapi/core.js"),et=e("common/utils.js"),tt=e("appmsg/emotion/selection.js"),nt=e("appmsg/i18n.js"),ot=e("biz_common/dom/event.js"),it=e("biz_wap/utils/ajax.js"),mt=e("biz_common/tmpl.js"),dt=e("biz_wap/utils/fakehash.js"),st=e("appmsg/log.js"),at=e("appmsg/my_comment_tpl.html.js"),ct=e("appmsg/emotion/dom.js"),lt=e("pages/utils.js"),rt=e("biz_wap/utils/mmversion.js"),_t=e("common/comm_report.js"),pt=e("biz_wap/utils/position.js"),ut=!window.isPaySubscribe||window.isPaySubscribe&&window.isPaid,gt={
Bizuin_from:window.biz,
Msgid_from:window.parseInt(window.mid,10)||0,
Itemidx_from:window.parseInt(window.idx,10)||0,
Scene:window.parseInt(window.source,10)||0,
Subscene:window.parseInt(window.subscene,10)||0,
Sessionid:window.sessionid||"",
Enterid:window.parseInt(window.enterid,10)||0,
Useruin:1*window.user_uin
},ft=0;
try{
ft=1*window.atob(window.biz);
}catch(wt){}
var yt={
BizUin:ft,
BizUinStr:window.biz||"",
AppMsgId:window.parseInt(window.mid,10)||0,
ItemIdx:window.parseInt(window.idx,10)||0,
ItemShowType:window.parseInt(window.item_show_type,10)||0,
SessionIdStr:window.sessionid||"",
EnterId:window.parseInt(window.enterid,10)||0,
Scene:window.parseInt(window.source,10)||0,
SubScene:window.parseInt(window.subscene,10)||0
},ht={
scene:0,
idkey:"",
moreList:27,
repeatList:25,
errList:18,
handleList:26,
addCommentErr:19,
errComment:18,
repeatContent:24,
repeatContentID:23
},jt=void 0,Ct=void 0,bt=void 0,vt=void 0,It=void 0,Bt=void 0,kt=window.comment_id,Et=0,Tt=void 0,xt=!1,Mt="",Pt=!1,Ht=0,Lt=[],St={},Dt=[],zt="",At="我",Rt=0,Nt={},Ft=Date.now(),Ot=!1,qt=void 0,Ut=void 0,Wt=100,Gt=location.href,Yt=J.os.pc,Vt="comment_editing",Qt="my_comment_empty_data",Jt=navigator.userAgent.indexOf("MicroMessenger")>-1,Xt=document.getElementById("js_cmt_area"),Zt=document.getElementById("js_friend_cmt_area"),$t=document.getElementById("js_cmt_container"),Kt=Gt.indexOf("vconsole=1")>0||document.cookie&&document.cookie.indexOf("vconsole_open=1")>-1,en=e(Yt?"appmsg/emotion/emotion_pc.js":"appmsg/emotion/emotion.js"),tn="http://mmbiz.qpic.cn/mmbiz/ByCS3p9sHiak6fjSeA7cianwo25C0CIt5ib8nAcZjW7QT1ZEmUo4r5iazzAKhuQibEXOReDGmXzj8rNg/0",nn=["“”","‘’","（）","《》","〈〉","「」","『』","〔〕","【】","［］","[]","｛｝","{}","()","<>"],on=function(e){
K.invoke("setNavigationBarColor",{
color:e
}),K.invoke("setBounceBackground",{
backgroundColor:e
});
},mn=window.isOldVideoPage,dn=window.matchMedia("(prefers-color-scheme: dark)"),sn=function(e){
var t=e.matches;
Ot=t,et.isNativePage()||on(G.hasClass(document.body,Vt)?mn||Ot?"#191919":"#ffffff":mn||Ot?"#232323":"#ffffff");
};
return dn.addListener(sn),sn(dn),window.pageCommentReportData&&window.pageCommentReportData.idkey&&(Kt&&console.log("init reportData"),
ht=window.pageCommentReportData),"undefined"!=typeof window.comment_id?kt=window.comment_id:window.cgiData&&"undefined"!=typeof window.cgiData.comment_id&&(kt=window.cgiData.comment_id),
Jt||(Xt&&(Xt.style.display="none"),Zt&&(Zt.style.display="none"),kt=0),Kt&&console.info("[图文评论] 评论ID:",kt),
W(),{
initComment:U,
getCommentData:j,
renderComment:h
};
});define("appmsg/like.js",["biz_common/dom/event.js","biz_common/dom/class.js","biz_wap/utils/ajax.js","biz_common/base64.js","appmsg/log.js","complain/tips.js","appmsg/retry_ajax.js","biz_wap/jsapi/core.js","biz_wap/utils/mmversion.js","common/utils.js","appmsg/loading.js","appmsg/i18n.js","biz_wap/utils/device.js","appmsg/pay_report_utils.js"],function(require,exports,module,alert){
"use strict";
function qs(e){
return document.getElementById(e);
}
function showAppToast(e,i){
JSAPI.invoke("handleMPPageAction",{
action:"showToast",
wording:e||"",
status:i||"success"
});
}
function initLikeEvent(opt){
function show(e){
e.style.display="";
}
function hide(e){
e.style.display="none";
}
function vShow(e){
e.style.visibility="visible";
}
function vHide(e){
e.style.visibility="hidden";
}
function clear(e){
e.value="";
}
function showLoading(){
commonUtils.isNativePage()?showAppToast("发送中","loading"):Loading.show("发送中");
}
function hideLoading(){
commonUtils.isNativePage()?showAppToast("","dismissloading"):Loading.hide();
}
function showToast(e){
commonUtils.isNativePage()?showAppToast(e):(el_toastMsg.innerHTML=e,show(el_likeToast),
setTimeout(function(){
hide(el_likeToast);
},1e3));
}
function newAlert(e){
el_alertContent.innerHTML=e,el_alertPanel.style.display="";
}
function alert2(e){
"0"===window.item_show_type?newAlert(e):alert(e);
}
function failAlert(e){
return e&&e.length>maxLikeCommentWord?void alert2("想法不可以超过%s字".replace("%s",maxLikeCommentWord)):void alert2("网络异常，请稍后重试");
}
function isAppCommentAvailable(){
return mmversion.isWechat?Device.os.ipad?!1:mmversion.isInMiniProgram?!1:mmversion.isIOS&&mmversion.gtVersion("7.0.8")?!0:mmversion.isAndroid&&mmversion.gtVersion("7.0.8")?!0:commonUtils.isNativePage()&&(mmversion.isIOS||mmversion.isAndroid)?!0:!1:!1;
}
var scrollTop,el_like=opt.likeAreaDom,el_likeNum=opt.likeNumDom,showType=opt.showType,prompted=opt.prompted,haokanLock=!1,startY,jumpWowLock=!1,el_likeToast=qs("js_like_toast"),el_likeBtn=qs("js_like_btn"),el_toastMsg=qs("js_toast_msg"),el_likeEducate=qs("js_like_educate"),el_friend_like=qs("js_friend_like_area"),el_go_wow=qs("js_go_wow"),el_likeComment=qs("js_like_comment"),el_bcommentPanel2=qs("js_comment_panel"),el_likeCommentShare=qs("js_like_comment_share"),el_likeCommentText=qs("js_comment_text"),el_commentCancel=qs("js_comment_cancel"),el_commentConfirm=qs("js_comment_confirm"),el_commentErrorMsg=qs("js_like_comment_msg"),el_commentCurrentCount=qs("js_like_current_cnt"),el_commentArea=qs("js_comment_area"),el_wowClosePanel=qs("wow_close_inform"),el_wowCloseAck=qs("wow_close_ack"),el_alertPanel=qs("js_alert_panel"),el_alertContent=qs("js_alert_content"),el_alertConfirm=qs("js_alert_confirm");
if(el_like&&el_likeNum){
var img=new Image;
window.appmsg_like_type&&2===window.appmsg_like_type?img.src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=114217_0_1":window.appmsg_like_type&&1===window.appmsg_like_type&&(img.src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=114217_1_1");
var like_report=function(){
log("[Appmsg] click like");
var e=el_like.getAttribute("like"),i=el_likeNum.innerHTML,o=parseInt(e)?parseInt(e):0,t=o?0:1,n=parseInt(i)?parseInt(i):0,s=opt.appmsgid||opt.mid,l=opt.itemidx||opt.idx;
if(o){
if(1!==appmsg_like_type)return void sendRecommendAjax(0);
Class.removeClass(el_like,opt.className),el_like.setAttribute("like",0),n>0&&"100000+"!==i&&(el_likeNum.innerHTML=n-1==0?"赞":n-1);
}else if(1===appmsg_like_type)el_like.setAttribute("like",1),Class.addClass(el_like,opt.className),
"100000+"!==i&&(el_likeNum.innerHTML=n+1);else if(2===appmsg_like_type)return void initRecommendPanel();
RetryAjax({
url:"/mp/appmsg_like?__biz="+opt.biz+"&mid="+opt.mid+"&idx="+opt.idx+"&like="+t+"&f=json&appmsgid="+s+"&itemidx="+l,
data:{
is_temp_url:opt.is_temp_url||0,
scene:window.source,
subscene:window.subscene,
appmsg_like_type:window.appmsg_like_type,
item_show_type:parseInt(window.item_show_type,10),
client_version:window.clientversion,
action_type:t?1:2,
device_type:window.devicetype
},
type:"POST"
});
},initRecommendPanel=function(){
sendRecommendAjax(1,"",1);
},isBeenUnvisible=function(e){
function i(){
return window.pageYOffset||document.documentElement.scrollTop||document.body.scrollTop||0;
}
return e.offsetTop+el_likeComment.offsetHeight-i()>=commonUtils.getInnerHeight()?!0:!1;
},disableMove=function(){
document.addEventListener("touchmove",preventMove,{
passive:!1
}),el_likeCommentText.addEventListener("touchstart",getTouchStart,{
passive:!1
}),el_likeCommentText.addEventListener("touchmove",preventText,!1);
},enableMove=function(){
document.removeEventListener("touchmove",preventMove,{
passive:!1
}),el_likeCommentText.removeEventListener("touchstart",getTouchStart,{
passive:!1
}),el_likeCommentText.removeEventListener("touchmove",preventText,!1);
},preventMove=function(e){
var i=e.target;
"TEXTAREA"!==i.tagName&&"BUTTON"!==i.tagName&&(e.preventDefault(),e.stopPropagation());
},getTouchStart=function(e){
var i=e.targetTouches||[];
if(i.length>0){
var o=i[0]||{};
startY=o.clientY;
}
},preventText=function(e){
var i=!1,o=e.changedTouches,t=this.scrollTop,n=this.offsetHeight,s=this.scrollHeight;
if(o.length>0){
var l=o[0]||{},a=l.clientY;
i=a>startY&&0>=t?!1:startY>a&&t+n>=s?!1:!0,i||e.preventDefault();
}
},isShow=function(e){
return"none"===e.style.display||"hidden"===e.style.visibility?!1:""===e.style.display||"block"===e.style.display||"visible"===e.style.visibility?!0:void 0;
},validataComment=function(e,i){
var o=e.value.replace(/^\s+|\s+$/g,"");
sendRecommendAjax(1,o,i);
},showEducatePanel=function(e,i,o){
show(el_likeComment);
var t=window.source||window.cgiData&&window.cgiData.source||0;
return t&&(t=parseInt(t,10),94===t)?void(e&&5===e&&hide(el_likeComment)):void(i||(show(el_likeEducate),
o&&o>0&&(el_friend_like.innerHTML="%s位朋友也在看,".replace("%s",o),document.getElementById("js_friend_like_word").innerText="前往“发现”-“看一看”浏览",
show(el_friend_like)),1===showType&&(hide(el_go_wow),hide(el_likeCommentShare)),
isBeenUnvisible(el_likeComment)&&scrollToShow(el_likeComment),educateExpose()));
},setBtnLike=function(){
el_like.setAttribute("like",1),Class.addClass(el_likeBtn,opt.className),realLikeNum+=1;
var e=el_likeNum.innerHTML;
"10万+"!==e&&(el_likeNum.innerHTML=dealLikeReadShow(realLikeNum));
},setLike2Status=function(e,i,o){
var t="在看";
switch(showType){
case 1:
switch(prompted){
case 0:
showEducatePanel(e,i,o),show(el_likeComment),prompted=1;
break;

case 1:
hide(el_likeEducate),showToast(t);
}
setBtnLike();
break;

case 2:
switch(hide(el_bcommentPanel2),clear(el_likeCommentText),prompted){
case 0:
showEducatePanel(e,i,o),5===e&&hide(el_likeCommentShare);
break;

case 1:
(4===e||5===e)&&showToast(4===e?"已发送":t);
}
5!==e&&(4===e&&"none"!==el_likeEducate.style.display?hide(el_likeCommentShare):4===e?hide(el_likeComment):(show(el_commentArea),
show(el_likeCommentShare),1===prompted&&hide(el_likeEducate),show(el_likeComment),
isBeenUnvisible(el_likeComment)&&scrollToShow(el_likeComment))),4!==e&&setBtnLike(),
prompted=1;
}
enableMove(),commonUtils.isNativePage()&&JSAPI.invoke("handleHaokanAction",{
action:"closeComment"
});
},unsetLike2Status=function(e){
1===e?setTimeout(function(){
alert2(" 已取消，想法已同步删除");
},20):showToast("已取消"),2===showType&&isShow(el_likeComment)&&hide(el_likeComment);
var i=el_likeNum.innerHTML;
Class.removeClass(el_likeBtn,opt.className),el_like.setAttribute("like",0),el_likeComment&&hide(el_likeComment),
realLikeNum-=1,realLikeNum>=0&&"10万+"!==i&&(el_likeNum.innerHTML=dealLikeReadShow(realLikeNum));
},sendRecommendAjax=function sendRecommendAjax(like,comment,type,clientType){
if(!haokanLock){
showLoading();
var appmsgid=opt.appmsgid||opt.mid,itemidx=opt.itemidx||opt.idx;
haokanLock=!0;
var action_type;
like?(window.isPaySubscribe&&payReportUtils.reportPayAppmsg(12),action_type=type):(window.isPaySubscribe&&payReportUtils.reportPayAppmsg(13),
action_type=2),ajax({
url:"/mp/appmsg_like?__biz="+opt.biz+"&mid="+opt.mid+"&idx="+opt.idx+"&like="+like+"&f=json&appmsgid="+appmsgid+"&itemidx="+itemidx,
data:{
is_temp_url:opt.is_temp_url||0,
scene:window.source,
subscene:window.subscene,
appmsg_like_type:window.appmsg_like_type,
item_show_type:parseInt(window.item_show_type,10),
client_version:window.clientversion,
comment:comment?comment:"",
prompted:1,
style:clientType||showType,
action_type:action_type,
passparam:window.passparam,
request_id:(new Date).getTime(),
device_type:window.devicetype
},
type:"POST",
success:function success(res){
haokanLock=!1;
var data=eval("("+res+")");
hideLoading(),0==data.base_resp.ret?(like?setLike2Status(type,data.is_eu_user,data.friend_like_num):unsetLike2Status(data.has_comment),
connectWithApp(like,comment,clientType)):failAlert(comment);
},
error:function(){
hideLoading(),failAlert(),haokanLock=!1;
}
});
}
};
JSAPI.on("menu:haokan",function(e){
var i=0===parseInt(e.recommend)?0:1;
if(0===i)sendRecommendAjax(i,"",2,clientShowType);else{
var o="";
o=e.comment;
var t=1===e.scene?4:5;
sendRecommendAjax(i,o,t,clientShowType);
}
});
var connectWithApp=function(e,i){
var o={
origin:"mp",
isLike:e?1:0,
url:encodeURIComponent(msg_link.html(!1)),
content:i?i:""
};
JSAPI.invoke("handleHaokanAction",{
action:actionString,
recommend:e?1:0,
server_data:JSON.stringify(o)
},function(e){
console.log("handleHaokanAction",e);
}),JSAPI.invoke("handleHaokanAction",{
action:actionForClient,
permission:1,
recommend:e?1:0
},function(e){
console.log("handleHaokanAction for client",e);
});
},goWoW=function(){
jumpWowLock||(jumpToWowClickReport(),jumpWowLock=!0,JSAPI.invoke("handleHaokanAction",{
action:"jumpToWow",
extParams:JSON.stringify({
autoDropLoad:!0
})
},function(e){
jumpWowLock=!1,console.log("jumpToWow",e),e.err_msg&&"handleHaokanAction:fail_entrance_not_open"===e.err_msg?show(el_wowClosePanel):"handleHaokanAction:fail  action not support"===e.err_msg||"handleHaokanAction:fail, action not support"===e.err_msg?alert2("微信版本过低，暂不支持该操作"):"handleHaokanAction:ok"===e.err_msg&&hide(el_likeComment),
JSAPI.invoke("handleHaokanAction",{
action:actionString,
server_data:JSON.stringify({
origin:"mp",
autoDropLoad:!0
})
},function(e){
console.log("sendAutoDropLoad",e);
});
}));
},likeClickReport=function(){
ajax({
url:"/mp/appmsgreport?action=appmsglikeclickcomment&__biz="+opt.biz+"&mid="+opt.mid+"&idx="+opt.idx+"&f=json&appmsgid="+appmsgid+"&itemidx="+itemidx,
data:{
is_temp_url:opt.is_temp_url||0,
scene:window.source,
subscene:window.subscene,
appmsg_like_type:window.appmsg_like_type,
item_show_type:parseInt(window.item_show_type,10),
client_version:window.clientversion,
device_type:window.devicetype
},
type:"POST"
});
},likeExpose=function e(){
var i=document.documentElement.scrollTop||window.pageYOffset||document.body.scrollTop,o=qs("like3").offsetTop,t=opt.appmsgid||opt.mid,n=opt.itemidx||opt.idx;
i+commonUtils.getInnerHeight()>o&&o>=i&&(ajax({
url:"/mp/appmsgreport?action=appmsglikeexposure&__biz="+opt.biz+"&mid="+opt.mid+"&idx="+opt.idx+"&f=json&appmsgid="+t+"&itemidx="+n,
data:{
is_temp_url:opt.is_temp_url||0,
scene:window.source,
subscene:window.subscene,
appmsg_like_type:window.appmsg_like_type,
item_show_type:parseInt(window.item_show_type,10),
client_version:window.clientversion,
device_type:window.devicetype
},
type:"POST"
}),DomEvent.off(window,"scroll",e));
},educateExpose=function i(){
var e=(document.documentElement.scrollTop||window.pageYOffset||document.body.scrollTop,
opt.appmsgid||opt.mid),o=opt.itemidx||opt.idx,t=window.item_show_type,n=window.enterid||window.cgiData&&window.cgiData.enterid||"";
el_likeEducate&&"none"!=el_likeEducate.style.display&&commonUtils.getInnerHeight()>el_likeEducate.getBoundingClientRect().top&&el_likeEducate.getBoundingClientRect().top+el_likeEducate.getBoundingClientRect().height>0&&(ajax({
url:"/mp/webcommreport?action=report&report_useruin=1&__biz="+window.biz,
type:"POST",
data:{
logid:18266,
buffer:["",Base64.decode(opt.biz),e,o,window.source,window.subscene,1,t,sessionid,n]
},
async:!1,
timeout:2e3
}),DomEvent.off(window,"scroll",i));
},jumpToWowClickReport=function(){
var e=opt.appmsgid||opt.mid,i=opt.itemidx||opt.idx,o=window.enterid||window.cgiData&&window.cgiData.enterid||"";
ajax({
url:"/mp/webcommreport?action=report&report_useruin=1&__biz="+window.biz,
type:"POST",
data:{
logid:18266,
buffer:["",Base64.decode(opt.biz),e,i,window.source,window.subscene,2,window.item_show_type,sessionid,o]
},
async:!1,
timeout:2e3
});
};
DomEvent.on(el_alertConfirm,"click",function(){
el_alertPanel.style.display="none";
}),DomEvent.on(el_like,"click",function(e){
return e.currentTarget.classList.contains("js_disabled")?!1:(like_report(e),!1);
}),DomEvent.on(el_wowCloseAck,"click",function(){
hide(el_wowClosePanel);
}),DomEvent.on(qs("js_mask_2"),"mousedown",function(){
hide(el_bcommentPanel2),clear(el_likeCommentText),vHide(el_commentErrorMsg),enableMove();
}),DomEvent.on(el_commentConfirm,"mousedown",function(){
validataComment(el_likeCommentText,4);
}),DomEvent.on(el_commentCancel,"mousedown",function(){
hide(el_bcommentPanel2),clear(el_likeCommentText),vHide(el_commentErrorMsg),enableMove();
}),DomEvent.on(el_likeCommentShare,"click",function(){
return commonUtils.isNativePage()?void JSAPI.invoke("handleHaokanAction",{
action:"writeComment",
style:window.isOldVideoPage?"black":"white"
}):(scrollTop=document.body.scrollTop||document.documentElement.scrollTop,show(el_bcommentPanel2),
el_likeCommentText.focus(),el_commentConfirm.setAttribute("disabled","disabled"),
disableMove(),void likeClickReport());
}),DomEvent.on(el_likeCommentText,"focus",function(){}),DomEvent.on(el_likeCommentText,"blur",function(){
window.scrollTo(0,scrollTop);
}),DomEvent.on(window,"scroll",likeExpose),DomEvent.on(window,"scroll",educateExpose),
DomEvent.on(el_go_wow,"click",goWoW);
var scrollToShow=function(e){
e.scrollIntoView(!1);
};
DomEvent.on(el_likeCommentText,"input",function(e){
var i=el_likeCommentText.value.replace(/^\s+|\s+$/g,"");
i.length>maxLikeCommentWord?(el_commentCurrentCount.innerHTML=i.length,vShow(el_commentErrorMsg)):vHide(el_commentErrorMsg),
i.length>0&&i.length<=maxLikeCommentWord?el_commentConfirm.removeAttribute("disabled"):el_commentConfirm.setAttribute("disabled","disabled"),
Device.os.ios&&e.data&&doubleInputChar.indexOf(e.data)>-1&&(focusTag=!0);
}),DomEvent.on(el_likeCommentText,"click",function(){
Device.os.ios&&focusTag&&(el_likeCommentText.blur(),el_likeCommentText.focus(),focusTag=!1);
});
}
}
function showLikeNum(e){
var i=e||{};
if(i.show){
var o=i.likeAreaDom,t=i.likeNumDom,n=document.getElementById("js_like_btn");
o&&(o.style.display=i.likeAreaDisplayValue,o.style.visibility="",i.liked&&(1===appmsg_like_type?Class.addClass(o,i.className):Class.addClass(n,i.className)),
o.setAttribute("like",i.liked?"1":"0"));
var s=1===appmsg_like_type?"赞":"";
realLikeNum=i.likeNum||s,1===appmsg_like_type?(parseInt(realLikeNum)>1e5?realLikeNum="100000+":"",
t&&(t.innerHTML=realLikeNum)):2===appmsg_like_type&&(t.innerHTML=dealLikeReadShow(realLikeNum));
}
}
function dealLikeReadShow(e){
if("en"==LANG)return i18n.dealLikeReadShow_en(e);
var i="";
if(parseInt(e)>1e5)i="10万+";else if(parseInt(e)>1e4&&parseInt(e)<=1e5){
var o=""+parseInt(e)/1e4,t=o.indexOf(".");
i=-1===t?o+"万":o.substr(0,t)+"."+o.charAt(t+1)+"万";
}else i=0===parseInt(e)?"":e;
return i;
}
function showReadNum(e){
var i=e||{};
if(i.show){
var o=i.readAreaDom,t=i.readNumDom;
o&&(o.style.display=i.readAreaDisplayValue);
var n=i.readNum||1,s=window.ori_send_time||window.cgiData&&window.cgiData.ori_send_time||0,l=/(WindowsNT)|(Windows NT)|(Macintosh)/i.test(navigator.userAgent),a=1566025200,m=1565971200,r=Device.os.ios||l?a:m;
parseInt(s,10)>r&&window.item_show_type&&"5"===window.item_show_type&&("en"!=LANG&&(document.getElementById("readTxt").innerText="播放"),
n=i.videouv||0),1===appmsg_like_type?(parseInt(n)>1e5?n="100000+":"",t&&(t.innerHTML=n)):2===appmsg_like_type&&(t.innerHTML=dealLikeReadShow(n),
""===t.innerHTML&&(t.innerHTML="0"));
}
}
var DomEvent=require("biz_common/dom/event.js"),Class=require("biz_common/dom/class.js"),ajax=require("biz_wap/utils/ajax.js"),Base64=require("biz_common/base64.js"),log=require("appmsg/log.js"),Tips=require("complain/tips.js"),RetryAjax=require("appmsg/retry_ajax.js"),JSAPI=require("biz_wap/jsapi/core.js"),actionString="submitMsgToTL",actionForClient="update_recommend_status",mmversion=require("biz_wap/utils/mmversion.js"),commonUtils=require("common/utils.js"),Loading=require("appmsg/loading.js"),realLikeNum,clientShowType=5,i18n=require("appmsg/i18n.js"),Device=require("biz_wap/utils/device.js"),payReportUtils=require("appmsg/pay_report_utils.js"),maxLikeCommentWord=200,focusTag=!1,doubleInputChar=["“”","‘’","（）","《》","〈〉","「」","『』","〔〕","【】","［］","[]","｛｝","{}","()","<>"];
return{
initLikeEvent:initLikeEvent,
showLikeNum:showLikeNum,
showReadNum:showReadNum
};
});var _extends=Object.assign||function(e){
for(var t=1;t<arguments.length;t++){
var i=arguments[t];
for(var n in i)Object.prototype.hasOwnProperty.call(i,n)&&(e[n]=i[n]);
}
return e;
};
define("appmsg/related_article.js",["biz_common/utils/string/html.js","biz_common/tmpl.js","biz_wap/utils/ajax.js","appmsg/related_article_tpl.html.js","biz_wap/utils/openUrl.js","biz_common/dom/event.js","common/utils.js","biz_common/dom/class.js","biz_common/utils/url/parse.js","appmsg/i18n.js","common/comm_report.js"],function(e){
"use strict";
function t(){
return document.documentElement.scrollTop||document.body.scrollTop;
}
function i(e){
var t=document.createElement("div");
return t.innerHTML=e,t.childNodes;
}
function n(e){
a({
url:"/mp/relatedarticle?action=getlist&count=1&begin=0&article_url="+window.encodeURIComponent(location.href)+"&__biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx,
type:"GET",
dataType:"json",
success:function(t){
t&&t.list&&t.list.length>0&&(window.has_related_article=!0);
var n=function(){
if(t&&t.base_resp&&1*t.base_resp.ret===0)if(h=t.article_size||0,0===t.list.length)w.addClass(y,"hide");else{
b.style.display="block";
for(var e=t.list.map(function(e){
if("en"===window.LANG)e.read_num_wording=_.dealLikeReadShow_en(e.read_num);else if(window.parseInt(e.read_num)>1e5)e.read_num_wording="10万+";else if(window.parseInt(e.read_num)>1e4&&window.parseInt(e.read_num)<=1e5){
var t=""+window.parseInt(e.read_num)/1e4,i=t.indexOf(".");
e.read_num_wording=-1===i?t+"万":t.substr(0,i)+"."+t.charAt(i+1)+"万";
}else e.read_num_wording=0===window.parseInt(e.read_num)?"":e.read_num;
return e;
}),n=d.tmpl(m,{
list:e
}),o=i(n),r=0;r<o.length;r++)f.appendChild(o[r].cloneNode(!0));
t.article_size>1&&w.removeClass(y,"hide");
}
};
"function"==typeof e?e("sucess",n):n();
},
error:function(){
"function"==typeof e&&e("error");
}
});
}
function o(e){
a({
type:"POST",
url:"/mp/relatedarticle?action=report_appmsg_expose&__biz="+window.biz,
async:!1,
timeout:2e3,
data:_extends(e,j)
});
}
function r(){
for(var e=document.getElementsByClassName("js_related_item"),i=t(),n=0;n<e.length;n++){
var r=e[n];
1*r.getAttribute("data-hasreport")!==1&&r.clientHeight+r.offsetTop>=i+r.clientHeight/2&&r.clientHeight+r.offsetTop<=i+r.clientHeight/2+l.getInnerHeight()&&!function(e,t){
var i=e.getAttribute("data-url"),n=e.getAttribute("data-time");
e.setAttribute("data-hasreport",1),o({
action_type:1,
type:1,
biz:u.getQuery("__biz",i),
mid:u.getQuery("mid",i),
idx:u.getQuery("idx",i),
send_timestamp:n,
pos:t+1
}),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_21_1&r="+Math.random(),
g.report(18832,_extends({
Actiontype:1,
Type:1,
Bizuin:u.getQuery("__biz",i),
Msgid:window.parseInt(u.getQuery("mid",i),10)||0,
Itemidx:window.parseInt(u.getQuery("idx",i),10)||0,
Sendtimestamp:window.parseInt(n)||0,
Pos:t+1
},z));
}(r,n);
}
h>1&&1*y.getAttribute("data-hasreport")!==1&&y.clientHeight+y.offsetTop>=i+y.clientHeight/2&&y.clientHeight+y.offsetTop<=i+y.clientHeight/2+l.getInnerHeight()&&!function(e){
e.setAttribute("data-hasreport",1),o({
action_type:1,
type:2
}),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_22_1&r="+Math.random(),
g.report(18832,_extends({
Actiontype:1,
Type:2,
Bizuin:0,
Msgid:0,
Itemidx:0,
Sendtimestamp:0,
Pos:0
},z));
}(y);
}
function s(){
p.on(f,"click",".js_related_item",function(e){
var t=e.delegatedTarget,i=t.getAttribute("data-url"),n=t.getAttribute("data-time");
o({
action_type:2,
type:1,
biz:u.getQuery("__biz",i),
mid:u.getQuery("mid",i),
idx:u.getQuery("idx",i),
send_timestamp:n,
pos:1
}),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_23_1&r="+Math.random(),
g.report(18832,_extends({
Actiontype:2,
Type:1,
Bizuin:u.getQuery("__biz",i),
Msgid:window.parseInt(u.getQuery("mid",i),10)||0,
Itemidx:window.parseInt(u.getQuery("idx",i),10)||0,
Sendtimestamp:window.parseInt(n)||0,
Pos:1
},z)),c.openUrlWithExtraWebview(i);
}),p.on(y,"click",function(){
return o({
action_type:2,
type:2
}),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=110809_24_1&r="+Math.random(),
g.report(18832,_extends({
Actiontype:2,
Type:2,
Bizuin:0,
Msgid:0,
Itemidx:0,
Sendtimestamp:0,
Pos:0
},z)),c.openUrlWithExtraWebview("https://mp.weixin.qq.com/mp/relatedarticle?action=page&begin=0&article_url="+window.encodeURIComponent(location.href)+"&__biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&sessionid="+(window.enterid||"")+"&enterid="+parseInt(Date.now()/1e3,0)+"&scene_from="+window.source+"&subscene_from="+window.subscene+"#wechat_redirect"),
!1;
}),p.on(window,"scroll",r);
}
e("biz_common/utils/string/html.js");
var d=e("biz_common/tmpl.js"),a=e("biz_wap/utils/ajax.js"),m=e("appmsg/related_article_tpl.html.js"),c=e("biz_wap/utils/openUrl.js"),p=e("biz_common/dom/event.js"),l=e("common/utils.js"),w=e("biz_common/dom/class.js"),u=e("biz_common/utils/url/parse.js"),_=e("appmsg/i18n.js"),g=e("common/comm_report.js"),b=document.getElementById("js_related_area"),f=document.getElementById("js_related"),y=document.getElementById("js_related_load_more"),h=0,j={
biz_from:window.biz,
mid_from:window.mid,
idx_from:window.idx,
sessionid:window.sessionid||"",
enterid:window.enterid||"",
scene:window.source,
subscene:window.subscene
},z={
Bizuin_from:window.biz,
Msgid_from:window.parseInt(window.mid,10)||0,
Itemidx_from:window.parseInt(window.idx,10)||0,
Scene:window.parseInt(window.source,10)||0,
Subscene:window.parseInt(window.subscene,10)||0,
Sessionid:window.sessionid||"",
Enterid:window.parseInt(window.enterid,10)||0
};
return s(),n;
});define("appmsg/share_tpl.html.js",[],function(){
return'<div class="rich_media_extra">\n    <a href="<#= url #>" class="share_appmsg_container appmsg_card_context flex_context">\n        <div class="flex_hd">\n            <i class="share_appmsg_icon"> </i>\n        </div>\n        <div class="flex_bd">\n            <div class="share_appmsg_title">分享给订阅用户</div>\n            <p class="share_appmsg_desc">可快速分享原创文章给你的公众号订阅用户</p>\n        </div>\n    </a>\n</div>\n';
});define("appmsg/appmsgext.js",["appmsg/log.js","biz_wap/utils/ajax.js","rt/appmsg/getappmsgext.rt.js","biz_common/utils/wxgspeedsdk.js"],function(e){
"use strict";
function s(e){
function s(e){
for(var s=window.location.href,t=s.indexOf("?"),i=s.substr(t+1),_=i.split("&"),a=0;a<_.length;a++){
var n=_[a].split("=");
if(n[0].toUpperCase()==e.toUpperCase())return n[1];
}
return"";
}
var r={
biz:"",
appmsg_type:"",
mid:"",
sn:"",
idx:"",
scene:"",
title:"",
ct:"",
abtest_cookie:"",
devicetype:"",
version:"",
is_need_ticket:0,
is_need_ad:0,
comment_id:"",
is_need_reward:0,
both_ad:0,
reward_uin_count:0,
send_time:"",
msg_daily_idx:"",
is_original:0,
is_only_read:0,
req_id:"",
pass_ticket:"",
is_temp_url:0,
more_read_type:0,
rtId:"",
rtKey:"",
appmsg_like_type:1,
related_video_sn:"",
vid:"",
is_pay_subscribe:0,
pay_subscribe_uin_count:0,
has_red_packet_cover:0,
onSuccess:function(){},
onError:function(){}
};
for(var d in e)e.hasOwnProperty(d)&&(r[d]=e[d]);
console.info("[(评论、点赞、赞赏) 发送请求]: ",new Date),i({
url:"/mp/getappmsgext?f=json&mock="+s("mock"),
data:{
r:Math.random(),
__biz:r.biz,
appmsg_type:r.appmsg_type,
mid:r.mid,
sn:r.sn,
idx:r.idx,
scene:r.scene,
title:encodeURIComponent(r.title.htmlDecode()),
ct:r.ct,
abtest_cookie:r.abtest_cookie,
devicetype:r.devicetype.htmlDecode(),
version:r.version.htmlDecode(),
is_need_ticket:r.is_need_ticket,
is_need_ad:r.is_need_ad,
comment_id:r.comment_id,
is_need_reward:r.is_need_reward,
both_ad:r.both_ad,
reward_uin_count:r.is_need_reward?r.reward_uin_count:0,
send_time:r.send_time,
msg_daily_idx:r.msg_daily_idx,
is_original:r.is_original,
is_only_read:r.is_only_read,
req_id:r.req_id,
pass_ticket:r.pass_ticket,
is_temp_url:r.is_temp_url,
item_show_type:r.item_show_type,
tmp_version:1,
more_read_type:r.more_read_type,
appmsg_like_type:r.appmsg_like_type,
related_video_sn:r.related_video_sn,
vid:r.vid,
is_pay_subscribe:r.is_pay_subscribe,
pay_subscribe_uin_count:r.pay_subscribe_uin_count,
has_red_packet_cover:r.has_red_packet_cover
},
type:"POST",
dataType:"json",
rtId:r.rtId,
rtKey:r.rtKey,
rtDesc:_,
async:!0,
success:function(e){
if(console.info("[(评论、点赞、赞赏) 响应请求]: ",new Date,e),t("[Appmsg] success get async data"),
"function"==typeof r.onSuccess&&r.onSuccess(e),e)try{
t("[Appmsg] success get async data, async data is: "+JSON.stringify(e));
}catch(s){}else t("[Appmsg] success get async data, async data is empty");
if(!n&&"5"===window.item_show_type){
var i=Date.now()-window.logs.pagetime.page_begin;
if(n=!0,Math.random()>.1)return;
a.saveSpeeds({
uin:window.uin,
pid:675,
speeds:[{
sid:29,
time:i
}]
}),a.send();
}
},
error:function(){
t("[Appmsg] error get async data, biz="+r.biz+", mid="+r.mid),"function"==typeof r.onError&&r.onError();
}
});
}
var t=e("appmsg/log.js"),i=e("biz_wap/utils/ajax.js"),_=e("rt/appmsg/getappmsgext.rt.js"),a=e("biz_common/utils/wxgspeedsdk.js"),n=void 0;
return{
getData:s
};
});define("appmsg/img_copyright_tpl.html.js",[],function(){
return'<span class="original_img_wrp">            \n    <span class="tips_global">来自: <#=source_nickname#></span>\n</span>    ';
});