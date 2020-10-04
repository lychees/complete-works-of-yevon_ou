define("pages/video_communicate_adaptor.js",["pages/player_tips.js"],function(t){
"use strict";
function e(){
window.addEventListener("message",i,!1),p();
}
function i(t){
var e;
if(t.origin?e=t.origin:t.originalEvent&&(e=t.originalEvent.origin),/^http(s)?\:\/\/mp\.weixin\.qq\.com$/.test(e)&&t.source){
var i=t.data;
if(i&&i.type){
if(!/^mpvideo_/.test(i.type))return;
var o=i.type.replace(/^mpvideo_/,"");
/^broadcast_/.test(o)?u.postMessageEvt.broadcast({
data:i.data,
type:o
}):u.postMessageEvt[o]&&u.postMessageEvt[o](i.data);
}
}
}
function o(t){
var e=t.type.replace(/^broadcast_/,""),i=d();
if(i.length>0)for(var o=0,a=i.length;a>o;o++){
var r=i[o];
n({
win:r.contentWindow,
type:e,
data:t.data
});
}
n({
win:window,
type:e,
data:t.data
});
}
function n(t){
var e=t.type;
/^mpvideo_/.test(e)||(e="mpvideo_"+e);
var i={
data:t.data,
type:e
};
t.win.postMessage(i,document.location.protocol+"//mp.weixin.qq.com");
}
function a(){
var t=arguments.length<=0||void 0===arguments[0]?{}:arguments[0];
t.msg&&new f({
msg:t.msg
});
}
function r(t){
for(var e=d({
vid:t.vid
}),i=0,o=e.length;o>i;i++){
var a=e[i];
a.style.display="";
var r=a.parentNode,s=r.querySelectorAll('.js_img_loading[data-vid="'+t.vid+'"]');
if(s&&s.length>0)for(var i=0,o=s.length;o>i;i++)r.removeChild(s[i]);
n({
type:"afterRemoveLoading",
win:a.contentWindow
});
}
}
function d(t){
t=t||{};
for(var e=document.getElementsByTagName("iframe"),i=[],o=0,n=e.length;n>o;o++){
var a=e[o],r=a.getAttribute("src");
if(window.__second_open__&&(r=a.getAttribute("data-realsrc")),r&&-1!=r.indexOf("/mp/videoplayer")){
if("undefined"!=typeof t.vid){
var d=r.match(/[\?&]vid\=([^&]*)/);
if(!d||!d[1]||d[1]!=t.vid)continue;
}
i.push(a);
}
}
return i;
}
function s(t){
if(t.height){
var e=d({
vid:t.vid
});
if(0!=e.length){
var i=e[0],o=i.offsetHeight+1*t.height;
i.setAttribute("height",o),i.setAttribute("data-additionalheight",t.height),i.style.setProperty&&i.style.setProperty("height",o+"px","important");
}
}
}
function v(t){
u.videoInfo[t.vid]||(u.videoInfo[t.vid]={}),u.videoInfo[t.vid].ori_status=t.ori_status,
u.videoInfo[t.vid].hit_bizuin=t.hit_bizuin,u.videoInfo[t.vid].hit_vid=t.hit_vid;
}
function p(){
"function"==typeof window.__getVideoWh&&window.addEventListener("resize",function(){
for(var t=d(),e=0,i=t.length;i>e;e++){
var o=t[e];
setTimeout(function(t){
return function(){
var e=window.__getVideoWh(t),i=e.w,o=e.h,n=1*t.getAttribute("data-additionalheight");
n&&(o+=n),t.setAttribute("width",i),t.setAttribute("height",o),t.style.setProperty&&(t.style.setProperty("width",i+"px","important"),
t.style.setProperty("height",o+"px","important"));
};
}(o),50);
}
},!1);
}
function g(){
return u.videoInfo;
}
var f=t("pages/player_tips.js"),u={
videoInfo:{},
postMessageEvt:{
broadcast:o,
removeVideoLoading:r,
addVideoIframeHeight:s,
videoInited:v,
showTips:a
}
};
return e(),{
getVideoInfo:g
};
});define("biz_wap/utils/ajax_wx.js",["biz_common/utils/string/html.js","biz_common/utils/url/parse.js","biz_wap/jsapi/core.js","biz_wap/utils/mmversion.js"],function(e){
"use strict";
function t(e){
var t={};
return"undefined"!=typeof uin&&(t.uin=uin),"undefined"!=typeof key&&(t.key=key),
"undefined"!=typeof pass_ticket&&(t.pass_ticket=pass_ticket),"undefined"!=typeof wxtoken&&(t.wxtoken=wxtoken),
"undefined"!=typeof window.devicetype&&(t.devicetype=window.devicetype),"undefined"!=typeof window.clientversion&&(t.clientversion=window.clientversion),
window.biz&&(t.__biz=window.biz),r.getQuery("enterid")&&(t.enterid=r.getQuery("enterid")),
"undefined"!=typeof appmsg_token?t.appmsg_token=appmsg_token:e.indexOf("advertisement_report")>-1&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=68064_13_1&r="+Math.random()),
t.x5=p?"1":"0",t.f="json",r.join(e,t);
}
function n(e,t){
return e.url.indexOf(t)>-1&&-1===e.url.indexOf("action=")&&(!e.data||!e.data.action);
}
function o(e){
var t=a.isIOS&&a.gtVersion("7.0.10",!0)||a.isAndroid&&a.gtVersion("7.0.12",!0);
s.invoke("currentMpInfo",{
userName:window.user_name,
brandName:t&&""===window.nickname&&""===window.nickname_new?"未命名公众号":window.title,
title:window.msg_title||"",
brandIcon:hd_head_img.replace(/\/0$/,"/132"),
itemShowType:window.item_show_type,
isPaySubscribe:window.isPaySubscribe,
topBarStyle:t?1:0,
topBarShowed:e
},function(){});
}
function i(e){
console.log(e),/^(http:\/\/|https:\/\/|\/\/)/.test(e.url)?/^\/\//.test(e.url)&&(e.url="https:"+e.url):e.url="https://mp.weixin.qq.com/"+e.url.replace(/^\//,""),
e.url+=-1==e.url.indexOf("?")?"?fasttmplajax=1":"&fasttmplajax=1","html"==e.f||-1!=e.url.indexOf("?f=json")&&-1!=e.url.indexOf("&f=json")||(e.url+="&f=json"),
e.notJoinUrl||"html"==e.f||(e.url=t(e.url));
var i=null;
if("object"==typeof e.data){
var p=e.data;
i=[];
for(var d in p)p.hasOwnProperty(d)&&i.push(d+"="+encodeURIComponent(p[d]));
i=i.join("&");
}else i="string"==typeof e.data?e.data:null;
console.log("before request");
var m=1,c=function(e,t){
return s.invoke("request",{
url:e.url,
method:e.type,
data:t,
header:{
Cookie:document.cookie
}
},function(i){
if(console.log("jsapiRequest",i.err_msg),i.err_msg.indexOf(":ok")>-1){
n(e,"/mp/getappmsgext")&&(window.receiveGetAppmsgExt=i.statusCode+"|"+Date.now()),
n(e,"/mp/getappmsgad")&&(window.receiveGetAppmsgAd=i.statusCode+"|"+Date.now());
var p={};
if(i.data){
console.log(e.dataType),console.log(e);
try{
if(p="json"==e.dataType?JSON.parse(i.data):i.data,p&&p.base_resp&&1*p.base_resp.ret!==0&&"undefined"!=typeof window.WX_BJ_REPORT&&window.WX_BJ_REPORT.BadJs&&Math.random()<.001){
var d=e.url;
-1!==url.indexOf("?")&&(d=url.substr(0,url.indexOf("?")),r.getQuery("action",url)&&(d=d+"?action="+r.getQuery("action",url))),
("/mp/getappmsgext"!==d&&"/mp/getappmsgad"!==d||"undefined"!=typeof p.base_resp.ret)&&window.WX_BJ_REPORT.BadJs.report(d,"ret="+p.base_resp.ret,{
mid:window.PAGE_MID,
view:"wap_retcode"
});
}
}catch(u){
return console.error(u),void(e.error&&e.error({},{
type:1,
error:u
}));
}
}
var l={};
try{
l=JSON.parse(i.data);
}catch(u){}
l.base_resp&&"-3"==l.base_resp.ret&&m>0&&(a.isIOS||a.isAndroid&&window.clientversion>27000600)?(m--,
s.invoke("updatePageAuth",{},function(n){
if(console.log("updatePageAuth",n),(new Image).src="https://mp.weixin.qq.com/mp/jsmonitor?idkey=112287_3_1",
n&&n.err_msg&&n.err_msg.indexOf(":ok")>-1){
window.top.pass_ticket=encodeURIComponent(r.getQuery("pass_ticket",n.fullUrl).html(!1).replace(/\s/g,"+")),
e.pass_ticket&&(e.pass_ticket=window.top.pass_ticket),console.warn("[skeleton] updatePageAuth resetTopbar");
var i=a.isIOS&&a.gtVersion("7.0.10",!0);
if("0"===window.item_show_type&&i){
var s=document.documentElement.scrollTop||window.pageYOffset||document.body.scrollTop||0;
o(s>40?!0:!1);
}
c(e,t),(new Image).src="https://mp.weixin.qq.com/mp/jsmonitor?idkey=112287_4_1";
}else e.success&&e.success(p);
})):e.success&&e.success(p);
}else if(i.err_msg.indexOf("no permission")>-1)Ajax(e),(new Image).src="https://mp.weixin.qq.com/mp/jsmonitor?idkey=112287_31_1";else{
e.error&&e.error({},i),(new Image).src="https://mp.weixin.qq.com/mp/jsmonitor?idkey=112287_32_1";
var w=.001;
if(Math.random()<w){
var f="request: "+JSON.stringify(e.type)+" "+JSON.stringify(e.url)+" ;;;; cookie: "+JSON.stringify(document.cookie)+" ;;;; data: "+JSON.stringify(t)+" ;;;; resp: "+JSON.stringify(i);
(new Image).src="https://badjs.weixinbridge.com/badjs?id=226&level=4&msg="+encodeURIComponent(f)+"&uin="+encodeURIComponent(window.uin)+"&from="+encodeURIComponent(window.location.href);
}
}
e.complete&&e.complete();
});
};
return n(e,"/mp/getappmsgext")&&(window.startGetAppmsgExtTime=Date.now()),n(e,"/mp/getappmsgad")&&(window.startGetAppmsgAdTime=Date.now()),
c(e,i);
}
e("biz_common/utils/string/html.js");
var r=e("biz_common/utils/url/parse.js"),s=e("biz_wap/jsapi/core.js"),a=e("biz_wap/utils/mmversion.js"),p=-1!=navigator.userAgent.indexOf("TBS/");
return{
ajax:i,
joinUrl:t
};
});define("biz_common/utils/respTypes.js",[],function(require,exports,module,alert){
"use strict";
var logList=[],log=function(r){
logList.push(r);
},printLog=function(){
for(var r=0,e=logList.length;e>r;++r)console.log("[RespType]"+logList[r]);
},isArray=function(r){
return"[object Array]"==Object.prototype.toString.call(r);
},getValueType=function(r){
return isArray(r)?"array":typeof r;
},parseRtDesc=function(r,e){
var t="mix",o=!1,c=e;
if(e){
var n="_R",s=e.indexOf(n),i=e.length-n.length;
o=-1!=s&&s==i,c=o?e.substring(0,i):e;
}
return"string"==typeof r?t=r:isArray(r)?t="array":"object"==typeof r&&(t="object"),
{
key:c,
type:t,
isRequired:o
};
},checkForArrayRtDesc=function(r,e){
if(!isArray(r))return!1;
for(var t=0,o=r.length;o>t;++t){
for(var c,n=r[t],s=0,i=0===e.length;c=e[s++];)if(checkForRtDesc(n,c)){
i=!0;
break;
}
if(!i)return!1;
}
return!0;
},checkForStringRtDesc=function(r,e){
var t=getValueType(r),o=parseRtDesc(e),c=o.type==t;
return c||log("miss match type : "+t+" !== "+o.type),c;
},checkForObjectRtDesc=function(r,e){
if("object"!=typeof r||isArray(r))return log("must be object"),!1;
var t=r,o=r;
for(var c in e)if(e.hasOwnProperty(c)){
var n=e[c],s=parseRtDesc(n,c),i=s.key;
o=t[i];
var u=getValueType(o);
if(s.isRequired&&void 0===o)return log("is required @key="+i),!1;
if(void 0!==o){
if(u!=s.type&&"mix"!=s.type)return log("miss match type : "+u+" !== "+s.type+" @key="+i),
!1;
if(("array"==u||"object"==u)&&"mix"!=s.type&&!checkForRtDesc(o,n))return!1;
}
}
return!0;
},checkForRtDesc=function(r,e){
return isArray(e)?checkForArrayRtDesc(r,e):"object"==typeof e?checkForObjectRtDesc(r,e):"string"==typeof e?checkForStringRtDesc(r,e):!1;
},check=function(json,rtDescs){
if("string"==typeof json)try{
json=eval("("+json+")");
}catch(e){
return log("parse json error"),!1;
}
if("object"!=typeof json)return log("must be object"),!1;
isArray(rtDesc)||(rtDescs=[rtDescs]);
for(var rtDesc,i=0;rtDesc=rtDescs[i++];)if(checkForRtDesc(json,rtDesc))return!0;
return!1;
};
return{
check:function(r,e){
logList=[];
try{
var t=check(r,e);
return t||printLog(),t;
}catch(o){
return logList.push("[rtException]"+o.toString()),printLog(),!1;
}
},
getMsg:function(){
return logList.join(";");
}
};
});define("biz_wap/utils/log.js",["biz_wap/utils/mmversion.js","biz_wap/jsapi/core.js"],function(i){
"use strict";
var s=i("biz_wap/utils/mmversion.js"),e=i("biz_wap/jsapi/core.js");
return function(i,n,o){
"string"!=typeof i&&(i=JSON.stringify(i)),n=n||"info",o=o||function(){};
var t;
s.isIOS?t="writeLog":s.isAndroid&&(t="log"),t&&e.invoke(t,{
level:n,
msg:"[WechatFe]"+i
},o);
};
});define("sougou/index.js",["appmsg/emotion/emotion.js","biz_common/tmpl.js","biz_wap/utils/ajax.js","biz_common/dom/event.js","biz_common/utils/string/html.js","sougou/a_tpl.html.js","appmsg/cmt_tpl.html.js","appmsg/my_comment_tpl.html.js"],function(t){
"use strict";
function e(t){
var e=document.getElementById("js_cover"),n=[];
e&&n.push(e);
var o=document.getElementById("js_content");
if(o)for(var i=o.getElementsByTagName("img")||[],s=0,r=i.length;r>s;s++)n.push(i.item(s));
for(var a=[],s=0,r=n.length;r>s;s++){
var l=n[s],c=l.getAttribute("data-src")||l.getAttribute("src");
c&&(a.push(c),function(e){
m.on(l,"click",function(){
return"ios"==t?window.JSInvoker&&window.JSInvoker.openImageList&&window.JSInvoker.openImageList(JSON.stringify({
index:e,
array:a
})):window.JSInvoker&&JSInvoker.weixin_openImageList&&window.JSInvoker.weixin_openImageList(JSON.stringify({
index:e,
array:a
})),!1;
});
}(s));
}
}
var n=t("appmsg/emotion/emotion.js"),o=t("biz_common/tmpl.js"),m=(t("biz_wap/utils/ajax.js"),
t("biz_common/tmpl.js"),t("biz_common/dom/event.js"));
t("biz_common/utils/string/html.js");
t("sougou/a_tpl.html.js"),t("appmsg/cmt_tpl.html.js");
if(document.getElementById("js_report_article3")&&(document.getElementById("js_report_article3").style.display="none"),
document.getElementById("js_toobar3")&&(document.getElementById("js_toobar3").style.display="none"),
function(){
var e=t("appmsg/my_comment_tpl.html.js"),n=document.createElement("div");
n&&(n.innerHTML=o.tmpl(e,{}),document.body.appendChild(n));
}(),n.init(),navigator.userAgent.toLowerCase().match(/ios/)){
var i=navigator.userAgent.toLowerCase().match(/(?:sogousearch\/ios\/)(.*)/);
if(i&&i[1]){
var s=i[1].replace(/\./g,"");
parseInt(s)>422&&e("ios");
}
}else e("android");
window.onerror=function(t){
var e=new Image;
e.src="/mp/jsreport?key=86&content="+t+"&r="+Math.random();
};
});define("biz_wap/safe/mutation_observer_report.js",[],function(){
"use strict";
window.addEventListener&&window.addEventListener("load",function(){
window.__moonsafe_mutation_report_keys||(window.__moonsafe_mutation_report_keys={});
var e=window.moon&&moon.moonsafe_id||29715,o=window.moon&&moon.moonsafe_key||0,t=[],n={},r=function(e){
return"[object Array]"==Object.prototype.toString.call(e);
},s=function(e,o,s){
s=s||1,n[e]||(n[e]=0),n[e]+=s,o&&(r(o)?t=t.concat(o):t.push(o)),setTimeout(function(){
a();
},1500);
},a=function(){
var r=[],s=t.length,i=["r="+Math.random()];
for(var c in n)n.hasOwnProperty(c)&&r.push(e+"_"+(1*c+1*o)+"_"+n[c]);
for(var c=0;s>c&&!(c>=10);++c)i.push("log"+c+"="+encodeURIComponent(t[c]));
if(!(0==r.length&&i.length<=1)){
var _,d="idkey="+r.join(";")+"&lc="+(i.length-1)+"&"+i.join("&");
if(window.ActiveXObject)try{
_=new ActiveXObject("Msxml2.XMLHTTP");
}catch(w){
try{
_=new ActiveXObject("Microsoft.XMLHTTP");
}catch(f){
_=!1;
}
}else window.XMLHttpRequest&&(_=new XMLHttpRequest);
_&&(_.open("POST",location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?",!0),_.setRequestHeader("cache-control","no-cache"),
_.setRequestHeader("Content-Type","application/x-www-form-urlencoded; charset=UTF-8"),
_.setRequestHeader("X-Requested-With","XMLHttpRequest"),_.onreadystatechange=function(){
4===_.readyState&&(t.length>10?(t=t.slice(10),a()):(t=[],n={}));
},t=[],n={},_.send(d));
}
};
try{
if(!window.__observer)return;
var i=window.__observer_data;
if(window.__observer.takeRecords){
var c=window.__observer.takeRecords();
if(c&&c.length){
i.count++;
var _=new Date;
c.forEach(function(e){
for(var o=e.addedNodes,t=0;t<o.length;t++){
var n=o[t];
if("SCRIPT"===n.tagName){
var r=n.src;
!r||/qq\.com/.test(r)||/weishi\.com/.test(r)||i.list.push(r);
}
}
}),i.exec_time+=new Date-_;
}
}
window.__observer.disconnect();
for(var d=window.__moonsafe_mutation_report_keys.observer||2,w=window.__moonsafe_mutation_report_keys.script_src||8,f=window.__moonsafe_mutation_report_keys.setattribute||9,u=window.__moonsafe_mutation_report_keys.ajax||10,m=25,v=0;v<i.list.length;v++){
var l=i.list[v],h=["[moonsafe][observer][url]:"+location.href,"[moonsafe][observer][src]:"+l,"[moonsafe][observer][ua]:"+navigator.userAgent];
i.list.length==v+1&&(h.push("[moonsafe][observer][count]:"+i.count),h.push("[moonsafe][observer][exec_time]:"+i.exec_time+"ms")),
s(d,h),"inlinescript_without_nonce"==l&&s(m,h);
}
var p=window.__danger_src;
if(p)for(var y=[{
key:"xmlhttprequest",
idkey:u
},{
key:"script_src",
idkey:w
},{
key:"script_setAttribute",
idkey:f
}],v=0;v<y.length;v++){
var b=y[v].key,g=p[b];
if(g&&g.length)for(var k=0;k<g.length;k++){
var h=["[moonsafe]["+b+"][url]:"+location.href,"[moonsafe]["+b+"][src]:"+g[k],"[moonsafe]["+b+"][ua]:"+navigator.userAgent];
s(y[v].idkey,h);
}
}
}catch(q){
var R=3,h=["[moonsafe][observer][exception]:"+q];
s(R,h);
}
},!1);
});define("appmsg/fereport.js",["biz_wap/utils/wapsdk.js","biz_common/utils/http.js","appmsg/log.js","biz_common/base64.js"],function(e){
"use strict";
function n(){
var e=window.performance||window.msPerformance||window.webkitPerformance;
if(e&&e.timing){
var n,i=e.timing,o=0,m=0,r=window.location.protocol,u=Math.random(),p=1>2*u,c=1>25*u,_=1>100*u,l=1>250*u,g=1>1e3*u,f=1>1e4*u,S=!0;
"https:"==r?(o=18,m=27,S=!1):"http:"==r&&(o=9,m=19);
var v=window.__wxgspeeds||{};
if(v&&v.moonloadtime&&v.moonloadedtime){
var B=v.moonloadedtime-v.moonloadtime;
n=localStorage&&JSON.parse(localStorage.getItem("__WXLS__moonarg"))&&"fromls"==JSON.parse(localStorage.getItem("__WXLS__moonarg")).method?21:22,
s.saveSpeeds({
sample:21==n||22==n&&g?1:0,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:n,
time:B
},
user_define:w
});
}
v&&v.mod_downloadtime&&s.saveSpeeds({
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:24,
time:v.mod_downloadtime
},
user_define:w
});
var h=i.domContentLoadedEventStart-i.navigationStart;
if(h>3e3&&(s.setBasicTime({
sample:_&&S||c&&!S?1:0,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:m
}),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_28_1&lc=1&log0="+window.encodeURIComponent(location.href)),
0==window.optimizing_flag?s.setBasicTime({
sample:g,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:467
}):1==window.optimizing_flag?s.setBasicTime({
sample:_,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:468
}):2==window.optimizing_flag&&s.setBasicTime({
sample:_,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:469
}),s.setBasicTime({
sample:l&&S||_&&!S?1:0,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o
}),d.htmlSize){
var I=d.htmlSize/(i.responseEnd-i.connectStart);
s.saveSpeeds({
sample:g,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:25,
time:Math.round(I)
},
user_define:w
});
}
if(v&&v.combo_times)for(var b=1;b<v.combo_times.length;b++)s.saveSpeeds({
sample:l,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:26,
time:v.combo_times[b]-v.combo_times[b-1]
},
user_define:w
});
if(v&&v.mod_num){
var R=v.hit_num/v.mod_num;
s.saveSpeeds({
sample:l,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:[{
sid:27,
time:Math.round(100*R)
},{
sid:28,
time:Math.round(1e3*R)
}],
user_define:w
});
}
var C=window.logs.pagetime.jsapi_ready_time-i.navigationStart;
s.saveSpeeds(156==o||155==o?{
sample:p,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:31,
time:C
},
user_define:w
}:{
sample:g,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:31,
time:C
},
user_define:w
}),s.send(),window.setTimeout(function(){
window.__moonclientlog&&t("[moon] "+window.__moonclientlog.join(" ^^^ "));
},250),window.setTimeout(function(){
window.onBridgeReadyTime&&(n=window.WeixinJSBridge&&window.WeixinJSBridge._createdByScriptTag?33:32,
s.saveSpeeds({
sample:f,
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:o,
speeds:{
sid:n,
time:window.onBridgeReadyTime-i.navigationStart
},
user_define:w
}),s.send());
},5e3);
}
}
function i(e){
for(var n=[],i=new DataView(e),o=0;o<i.byteLength;o+=4){
var s=i.getUint32(o),d=s.toString(16),t="00000000",a=(t+d).slice(-t.length);
n.push(a);
}
return n.join("");
}
function o(e,n){
var o=new TextEncoder("utf-8").encode(e),s=crypto.subtle||crypto.webkitSubtle;
return s.digest(n,o).then(function(e){
return i(e);
});
}
var s=e("biz_wap/utils/wapsdk.js"),d=e("biz_common/utils/http.js"),t=e("appmsg/log.js"),a=e("biz_common/base64.js"),w=a.toBase64(JSON.stringify({
scene:window.source,
sessionid:window.sessionid
}));
n(),function(){
try{
var e=Math.random(),n=window.localStorage,i=[],d=[];
for(var t in n)-1!=t.indexOf("__MOON__")&&window.moon_map[t.substr(8)]&&i.push(n[t]);
if(window.crypto){
var m="";
m=.5>e?"SHA-256":"SHA-1";
for(var r=(new Date).getTime(),u=0;u<i.length;u++)d.push(o(i[u],m));
Promise.all(d).then(function(){
var n=(new Date).getTime(),i=n-r;
s.saveSpeeds({
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:108,
speeds:{
sid:.5>e?21:23,
time:i
},
user_define:w
}),s.send();
});
}else s.saveSpeeds({
uin:window.encodeURIComponent(a.toBase64(window.user_uin))||uin,
pid:108,
speeds:{
sid:24,
time:1
},
user_define:w
}),s.send();
}catch(p){}
}();
});define("appmsg/fereport_without_localstorage.js",["biz_wap/utils/wapsdk.js","biz_common/utils/http.js","appmsg/log.js","biz_common/base64.js"],function(e){
"use strict";
function i(){
var e=window.performance||window.msPerformance||window.webkitPerformance;
if(e&&e.timing){
var i,a=e.timing,m=0,w=0,p=window.location.protocol,u=Math.random(),r=1>2*u,_=1>25*u,c=1>100*u,l=1>250*u,g=1>1e3*u,f=1>1e4*u,S=!0;
"https:"==p?(m=462,w=464,S=!1):"http:"==p&&(m=417,w=463);
var B=window.__wxgspeeds||{};
if(B&&B.moonloadtime&&B.moonloadedtime){
var v=B.moonloadedtime-B.moonloadtime;
i=localStorage&&JSON.parse(localStorage.getItem("__WXLS__moonarg"))&&"fromls"==JSON.parse(localStorage.getItem("__WXLS__moonarg")).method?21:22,
o.saveSpeeds({
sample:21==i||22==i&&g?1:0,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:i,
time:v
},
user_define:t
});
}
B&&B.mod_downloadtime&&o.saveSpeeds({
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:24,
time:B.mod_downloadtime
},
user_define:t
});
var I=a.domContentLoadedEventStart-a.navigationStart;
if(I>3e3&&(o.setBasicTime({
sample:c&&S||_&&!S?1:0,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:w
}),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_28_1&lc=1&log0="+encodeURIComponent(location.href)),
0==window.optimizing_flag?o.setBasicTime({
sample:g,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:473
}):1==window.optimizing_flag?o.setBasicTime({
sample:c,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:474
}):2==window.optimizing_flag&&o.setBasicTime({
sample:c,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:475
}),o.setBasicTime({
sample:l&&S||c&&!S?1:0,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m
}),n.htmlSize){
var R=n.htmlSize/(a.responseEnd-a.connectStart);
o.saveSpeeds({
sample:g,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:25,
time:Math.round(R)
},
user_define:t
});
}
if(B&&B.combo_times)for(var h=1;h<B.combo_times.length;h++)o.saveSpeeds({
sample:l,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:26,
time:B.combo_times[h]-B.combo_times[h-1]
},
user_define:t
});
if(B&&B.mod_num){
var C=B.hit_num/B.mod_num;
o.saveSpeeds({
sample:l,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:[{
sid:27,
time:Math.round(100*C)
},{
sid:28,
time:Math.round(1e3*C)
}],
user_define:t
});
}
var U=window.logs.pagetime.jsapi_ready_time-a.navigationStart;
o.saveSpeeds(156==m||155==m?{
sample:r,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:31,
time:U
},
user_define:t
}:{
sample:g,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:31,
time:U
},
user_define:t
}),o.send(),window.setTimeout(function(){
window.__moonclientlog&&s("[moon] "+window.__moonclientlog.join(" ^^^ "));
},250),window.setTimeout(function(){
window.onBridgeReadyTime&&(i=window.WeixinJSBridge&&window.WeixinJSBridge._createdByScriptTag?33:32,
o.saveSpeeds({
sample:f,
uin:window.encodeURIComponent(d.toBase64(window.user_uin))||uin,
pid:m,
speeds:{
sid:i,
time:window.onBridgeReadyTime-a.navigationStart
},
user_define:t
}),o.send());
},5e3);
}
}
var o=e("biz_wap/utils/wapsdk.js"),n=e("biz_common/utils/http.js"),s=e("appmsg/log.js"),d=e("biz_common/base64.js"),t=d.toBase64(JSON.stringify({
scene:window.source,
sessionid:window.sessionid
}));
i();
});define("appmsg/report.js",["biz_common/dom/event.js","biz_wap/utils/ajax.js","common/utils.js","appmsg/cdn_img_lib.js","biz_wap/utils/mmversion.js","biz_common/utils/report.js","biz_common/utils/monitor.js"],function(e){
"use strict";
function t(){
var t=(e("biz_wap/utils/mmversion.js"),e("biz_common/utils/report.js"),e("biz_common/utils/monitor.js")),r=!1,s=window.performance||window.msPerformance||window.webkitPerformance;
return function(){
return;
}(),s&&s.timing&&s.timing.navigationStart?(r=s.timing.navigationStart,function(){
return;
}(),function(){
function e(){
if(-1==i.indexOf("NetType/"))return!1;
for(var e=["2G","cmwap","cmnet","uninet","uniwap","ctwap","ctnet"],t=0,n=e.length;n>t;++t)if(-1!=i.indexOf(e[t]))return!0;
return!1;
}
var n=window.performance&&window.performance.timing,a=write_sceen_time-r,s=first_sceen__time-r,d=page_endtime-r,m=(window.onload_endtime||+new Date)-r;
-1!=navigator.userAgent.indexOf("MicroMessenger")&&(a=real_show_page_time-r,s=real_show_page_time-r);
var g=window.logs.jsapi_ready_time?window.logs.jsapi_ready_time-r:void 0,w=window.logs.a8key_ready_time?window.logs.a8key_ready_time-r:void 0,p=n&&n.connectEnd-n.connectStart,c=n&&n.secureConnectionStart&&n.connectEnd-n.secureConnectionStart,u=n&&n.domainLookupEnd&&n.domainLookupStart&&n.domainLookupEnd-n.domainLookupStart;
if(window.logs.pagetime.wtime=a,window.logs.pagetime.ftime=s,window.logs.pagetime.ptime=d,
window.logs.pagetime.onload_time=m,window.logs.pagetime.jsapi_ready_time=g,window.logs.pagetime.a8key_ready_time=w,
need_report_cost?o({
url:"/mp/report_cost",
type:"post",
data:{
id_key_list:["1|1|"+d,"1|2|"+s,"1|3|"+m,"1|4|"+g,"1|5|"+w,"1|6|"+p,"1|7|"+c,"1|8|"+u].join(";")
}
}):Math.random()<.01&&o({
url:"/mp/report_cost",
type:"post",
data:{
id_key_list:["#1|1|"+d,"1|2|"+s,"1|3|"+m,"1|4|"+g,"1|5|"+w,"1|6|"+p,"1|7|"+c,"1|8|"+u].join(";")
}
}),need_report_cost&&s>3e3){
var l=new Image,_=(new Date).getTime();
l.onload=function(){
var e=(new Date).getTime()-_,t=(new Date).getTime(),n=new Image;
n.onload=function(){
var n=(new Date).getTime()-t;
o({
url:"/mp/report_cost",
type:"post",
data:{
id_key_list:["^2|1|"+e,"2|2|"+n].join(";")
}
});
},n.src="http://ugc.qpic.cn/adapt/0/7d8963bb-aace-df23-0569-f8a4e388eacb/100?r="+Math.random();
},l.src="http://ugc.qpic.cn/adapt/0/7d8963bb-aace-df23-0569-f8a4e388eacb/100?r="+Math.random();
}
if(!(Math.random()>.2||0>m||0>a||0>s||0>d)){
if(g&&t.setAvg(27822,15,g),w&&t.setAvg(27822,17,w),d>=15e3)return t.setAvg(27822,29,d),
void t.send();
t.setAvg(27822,1,d).setAvg(27822,3,m).setAvg(27822,5,s),window.isWeixinCached&&t.setAvg(27822,19,d),
e()?(t.setAvg(27822,9,d),window.isWeixinCached&&t.setAvg(27822,23,d)):"wifi"==networkType?(t.setAvg(27822,7,d),
window.isWeixinCached&&t.setAvg(27822,21,d)):"2g/3g"==networkType?(t.setAvg(27822,11,d),
window.isWeixinCached&&t.setAvg(27822,25,d)):"4g"==networkType?(t.setAvg(27822,14,d),
window.isWeixinCached&&t.setAvg(27822,26,d)):(t.setAvg(27822,13,d),window.isWeixinCached&&t.setAvg(27822,28,d)),
window.moon&&moon.clearSample&&(t.setAvg(27822,71,d),e()?t.setAvg(27822,73,d):"wifi"==networkType?t.setAvg(27822,75,d):"2g/3g"==networkType?t.setAvg(27822,77,d):"4g"==networkType?t.setAvg(27822,78,d):t.setAvg(27822,79,d)),
p&&t.setAvg(27822,65,p),c&&t.setAvg(27822,67,c),u&&t.setAvg(27822,69,u),t.send();
}
}(),function(){
window.logs.jsapi_ready_fail&&(t.setSum(24729,55,window.logs.jsapi_ready_fail),t.send());
}(),function(){
var e=document.getElementById("js_toobar3"),t=document.getElementById("page-content");
if(t&&!(Math.random()>.1)){
var i=function o(){
var i=window.pageYOffset||document.documentElement.scrollTop,r=e.offsetTop;
if(i+a.getInnerHeight()>=r){
for(var d,m,g=t.getElementsByTagName("img"),w={},p=[],c=0,u=0,l=0,_=0,f=g.length;f>_;++_){
var v=g[_];
d=v.getAttribute("data-src")||v.getAttribute("src"),m=v.getAttribute("src"),d&&(d.isCDN()?u++:l++,
c++,w[m]={});
}
if(p.push("1="+1e3*c),p.push("2="+1e3*u),p.push("3="+1e3*l),s.getEntries){
var y=s.getEntries(),h=window.logs.img.download,k=[0,0,0],A=[0,0,0];
c=u=0;
for(var _=0,T=y.length;T>_;++_){
var j=y[_],b=j.name;
b&&"img"==j.initiatorType&&w[b]&&(b.isCDN()&&(A[0]+=j.duration,u++),k[0]+=j.duration,
c++,w[b]={
startTime:j.startTime,
responseEnd:j.responseEnd
});
}
k[0]>0&&c>0&&(k[2]=k[0]/c),A[0]>0&&u>0&&(A[2]=A[0]/u);
for(var _ in h)if(h.hasOwnProperty(_)){
for(var M=h[_],x=0,E=0,C=0,z=0,S=0,f=M.length;f>S;++S){
var d=M[S];
if(w[d]&&w[d].startTime&&w[d].responseEnd){
var D=w[d].startTime,I=w[d].responseEnd;
x=Math.max(x,I),E=E?Math.min(E,D):D,d.isCDN()&&(C=Math.max(x,I),z=E?Math.min(E,D):D);
}
}
k[1]+=Math.round(x-E),A[1]+=Math.round(C-z);
}
for(var W=4,N=7,_=0;3>_;_++)k[_]=Math.round(k[_]),A[_]=Math.round(A[_]),k[_]>0&&(p.push(W+_+"="+k[_]),
"wifi"==networkType?p.push(W+_+6+"="+k[_]):("2g/3g"==networkType||"4g"==networkType)&&p.push(W+_+12+"="+k[_])),
A[_]>0&&(p.push(N+_+"="+A[_]),"wifi"==networkType?p.push(N+_+6+"="+A[_]):("2g/3g"==networkType||"4g"==networkType)&&p.push(N+_+12+"="+A[_]));
}
n.off(window,"scroll",o,!1);
}
};
n.on(window,"scroll",i,!1);
}
}(),void function(){
if(!(Math.random()>.001)){
var e=document.createElement("iframe"),t=[600,800,1e3,1200,1500,2e3,3e3,5e3,1e4,18e3],n=Math.ceil(10*Math.random())-1,i=uin+mid+idx+Math.ceil(1e3*Math.random())+(new Date).getTime();
e.style.display="none",e.id="js_ajax",e.setAttribute("data-time",n),e.src="/mp/iframetest?action=page&traceid="+i+"&devicetype="+devicetype+"&timeout="+t[n];
var o=document.getElementById("js_article");
o.appendChild(e);
}
}()):!1;
}
var n=e("biz_common/dom/event.js"),i=navigator.userAgent,o=e("biz_wap/utils/ajax.js"),a=e("common/utils.js");
e("appmsg/cdn_img_lib.js"),n.on(window,"load",function(){
if(""==networkType&&window.isInWeixinApp()){
var e={
"network_type:fail":"fail",
"network_type:edge":"2g/3g",
"network_type:wwan":"2g/3g",
"network_type:wifi":"wifi"
};
JSAPI.invoke("getNetworkType",{},function(n){
networkType=e[n.err_msg],("network_type:edge"==n.err_msg||"network_type:wwan"==n.err_msg)&&(n.detailtype&&"4g"==n.detailtype||n.subtype&&"4g"==n.subtype)&&(networkType="4g"),
t();
});
}else t();
},!1);
});define("appmsg/report_and_source.js",["biz_common/utils/string/html.js","biz_common/dom/event.js","biz_common/utils/url/parse.js","appmsg/articleReport.js","biz_wap/utils/ajax.js","biz_wap/utils/mmversion.js","appmsg/open_url_with_webview.js","biz_wap/jsapi/core.js"],function(e,i,o,n){
"use strict";
function t(){
var e=window.location.protocol+"//",i=l.indexOf("://")<0?e+l:l;
if(-1!=i.indexOf("mp.weixin.qq.com/s")||-1!=i.indexOf("mp.weixin.qq.com/mp/appmsg/show")||-1!=i.indexOf("mp.weixin.qq.com/mp/homepage")){
var o=i.split("#");
i=s.addParam(o[0],"scene",25,!0)+(o[1]?"#"+o[1]:""),i=i.replace(/#rd$/g,"#wechat_redirect");
}else i=e+"mp.weixinbridge.com/mp/wapredirect?url="+encodeURIComponent(l);
try{
if("mp.weixin.qq.com"!=top.window.location.host)return window.top.open(i,"_blank"),
!1;
}catch(n){}
var t=location.search.replace("wx_header","del_wx_header"),r={
url:"/mp/advertisement_report"+t+"&report_type=3&action_type=0&url="+encodeURIComponent(l)+"&ascene="+encodeURIComponent(window.ascene||-1)+"&__biz="+biz+"&r="+Math.random(),
type:"GET",
mayAbort:!0,
async:!1
},m=p.isInMiniProgram?0:1;
return r.timeout=2e3,r.complete=function(){
_(i,{
sample:m,
scene:60,
user_name:user_name,
reject:function(){
location.href=i;
}
});
},a(r),!1;
}
e("biz_common/utils/string/html.js");
var r=e("biz_common/dom/event.js"),s=e("biz_common/utils/url/parse.js"),m=e("appmsg/articleReport.js"),a=e("biz_wap/utils/ajax.js"),p=e("biz_wap/utils/mmversion.js"),c=msg_title.htmlDecode(),l=msg_source_url.htmlDecode(),_=e("appmsg/open_url_with_webview.js"),d=e("biz_wap/jsapi/core.js");
m.init({
dom:document.getElementById("js_report_article3"),
title:c,
link:window.msg_link
});
var u=document.getElementById("js_view_source");
r.on(u,"click",function(){
return t(),!1;
});
});define("appmsg/appmsg_copy_report.js",["biz_wap/utils/ajax.js","biz_common/dom/event.js"],function(t){
"use strict";
var e=t("biz_wap/utils/ajax.js"),n=t("biz_common/dom/event.js"),o=function(t,e){
var n=!1,o=t;
if(t===e)n=!0;else for(;o.parentNode&&(o=o.parentNode,1!==o.nodeType||"body"!==o.tagName.toLowerCase());)if(o===e){
n=!0;
break;
}
return n;
},i=function(t){
this.biz=t.biz,this.logid=t.logid,this.baseData=t.baseData,this.isPaySubscribe=t.isPaySubscribe,
this.container=t.container,this.totalLength=this.container.innerText.length,this.initEvent();
};
return i.prototype.initEvent=function(){
var t=this;
n.on(document,"copy",function(){
console.log(t.getContentData());
var e=[].concat(t.baseData),n=t.getContentData().trim();
n.length&&(e.push(t.totalLength),e.push(n),e.push(n.length),e.push(t.isPaySubscribe),
t.report(e.join(",")));
});
},i.prototype.getContentData=function(){
var t=document.getSelection(),e=this.container,n="";
if(t&&t.rangeCount){
var i=t.getRangeAt(0);
if(!i.collapsed){
var a=i.startContainer,r=i.startOffset,s=i.endContainer,c=i.endOffset,p=o(a,e),u=o(s,e);
if(p&&u)n=i.toString();else if(p||u){
var f=document.createRange();
f.setStart(a,r),f.setEnd(s,c),!u&&f.setEndAfter(e),!p&&f.setStartBefore(e),n=f.toString();
}else if(t.containsNode&&t.containsNode(e,!0)){
var f=document.createRange();
f.setEndAfter(e),f.setStartBefore(e),n=f.toString();
}
}
}
return n;
},i.prototype.report=function(t){
var n=this.biz,o=this.logid;
e({
url:"/mp/webcommreport?action=report&report_useruin=1&__biz="+n,
type:"POST",
data:{
logid:o,
buffer:t
},
async:!1,
timeout:2e3
});
},i;
});define("appmsg/cdn_speed_report.js",["biz_common/dom/event.js","biz_wap/jsapi/core.js","biz_wap/utils/ajax.js"],function(e){
"use strict";
function t(){
function e(e){
var t=[];
for(var n in e)t.push(n+"="+encodeURIComponent(e[n]||""));
return t.join("&");
}
if(networkType){
var t=window.performance||window.msPerformance||window.webkitPerformance;
if(t&&"undefined"!=typeof t.getEntries){
var n,i,a=100,o=document.getElementsByTagName("img"),p=o.length,s=navigator.userAgent,g=!1;
/micromessenger\/(\d+\.\d+)/i.test(s),i=RegExp.$1;
for(var w=0,m=o.length;m>w;w++)if(n=parseInt(100*Math.random()),!(n>a)){
var d=o[w].getAttribute("src");
if(d&&!(d.indexOf("mp.weixin.qq.com")>=0)){
for(var f,_=t.getEntries(),u=0;u<_.length;u++)if(f=_[u],f.name==d){
var c=o[w].getAttribute("data-fail");
r({
type:"POST",
url:"/mp/appmsgpicreport?__biz="+biz+"#wechat_redirect",
data:e({
rnd:Math.random(),
uin:uin,
version:version,
client_version:i,
device:navigator.userAgent,
time_stamp:parseInt(+new Date/1e3),
url:d,
img_size:o[w].fileSize||0,
user_agent:navigator.userAgent,
net_type:networkType,
appmsg_id:window.appmsgid||"",
sample:p>100?100:p,
delay_time:parseInt(f.duration),
from:window.isSg?"sougou":"",
fail:c
})
}),g=!0;
break;
}
if(g)break;
}
}
}
}
}
var n=e("biz_common/dom/event.js"),i=e("biz_wap/jsapi/core.js"),r=e("biz_wap/utils/ajax.js"),a={
"network_type:fail":"fail",
"network_type:edge":"2g/3g",
"network_type:wwan":"2g/3g",
"network_type:wifi":"wifi"
};
i.invoke("getNetworkType",{},function(e){
networkType=a[e.err_msg],("network_type:edge"==e.err_msg||"network_type:wwan"==e.err_msg)&&(e.detailtype&&"4g"==e.detailtype||e.subtype&&"4g"==e.subtype)&&(networkType="4g"),
t();
}),n.on(window,"load",t,!1);
});define("appmsg/wxtopic.js",["biz_wap/utils/ajax.js","biz_wap/jsapi/core.js","biz_common/dom/event.js","appmsg/topic_tpl.html.js"],function(t){
"use strict";
function e(t){
t.parentNode.removeChild(t);
}
function i(t,e){
var i=c;
e.img_url||(e.img_url=topic_default_img);
for(var o in e){
var a=new RegExp("{"+o+"}","g");
i=i.replace(a,e[o]);
}
var p=document.createElement("span");
p.className="db topic_area",p.innerHTML=i,t.parentNode.insertBefore(p,t),t.parentNode.removeChild(t),
r.tap(p,function(){
var e=location.protocol+"//mp.weixin.qq.com/mp/topic?action=topic_detail_page&topic_id="+t.getAttribute("data-topic-id")+"&topic_type="+t.getAttribute("data-topic-type")+"&sn="+t.getAttribute("data-topic-sn")+"&scene=101#wechat_redirect";
n.invoke("openUrlWithExtraWebview",{
url:e,
openType:1
},function(t){
t&&-1!==t.err_msg.indexOf(":ok")||(location.href=e);
});
});
}
function o(t){
var o={
topic_id:t.getAttribute("data-topic-id"),
topic_type:t.getAttribute("data-topic-type"),
sn:t.getAttribute("data-topic-sn"),
biz:biz
};
p({
url:"/mp/topic?action=get_topic_info",
type:"post",
data:o,
success:function(o){
if(console.log(o),o=JSON.parse(o),0!=o.base_resp.ret)return void e(t);
var a={
title:o.title,
author:o.author||(o.leading_actor?o.leading_actor.replace(/\$\$/g," / "):"-"),
img_url:o.img_url,
msg_num:o.msg_num
};
i(t,a);
},
error:function(){
e(t);
}
});
}
function a(){
var t=document.getElementsByTagName("wxtopic");
t[0]&&o(t[0]);
}
var p=t("biz_wap/utils/ajax.js"),n=t("biz_wap/jsapi/core.js"),r=t("biz_common/dom/event.js"),c=t("appmsg/topic_tpl.html.js");
a();
});define("question_answer/appmsg.js",["biz_common/utils/string/html.js","question_answer/appmsg_tpl.html.js","biz_wap/utils/ajax.js","question_answer/utils.js","biz_common/dom/event.js","appmsg/weapp_common.js","biz_common/tmpl.js","pages/utils.js","biz_wap/utils/mmversion.js"],function(t){
"use strict";
t("biz_common/utils/string/html.js");
var e=t("question_answer/appmsg_tpl.html.js"),a=t("biz_wap/utils/ajax.js"),n=t("question_answer/utils.js"),i=t("biz_common/dom/event.js"),o=t("appmsg/weapp_common.js"),r=t("biz_common/tmpl.js"),p=(t("pages/utils.js"),
t("biz_wap/utils/mmversion.js"),!1),s=navigator.userAgent.match(/MicroMessenger\/(\d+)\.(\d+)\.(\d+)/);
if(s){
var d=Number(s[1]),m=Number(s[2]),u=Number(s[3]);
d>6?p=!0:6===d&&m>5?p=!0:6===d&&5===m&&u>=3&&(p=!0);
}
var c={
weapp_username:"gh_f960dd3580ec@app",
detailPath:"pages/detail/index",
profilePath:"pages/list/index",
topicPath:"pages/themes/index",
canJumpOnTap:p,
questionType:[1,2,3,3,2,1],
data:{},
batchGetQuestionParam:null,
retry:1
},l=function(t){
return document.getElementById(t);
},g=function(){
var t=l("js_content");
if(!t)return!1;
for(var e=t.getElementsByTagName("mp-question")||[],a=0,n=e.length;n>a;a++){
var i=e[a],o=window.biz,r=i.getAttribute("data-mid"),p=i.getAttribute("data-idx"),s=i.getAttribute("data-type")||c.questionType[a],d=o+"_"+a;
c.data[d]?c.data[d].invisibleElems.push(i):c.data[d]=1===s?{
invisibleElems:[i],
type:s,
mid:r,
idx:p,
dataStatus:1
}:{
invisibleElems:[i],
type:s,
dataStatus:1
};
}
return 0===e.length?!1:!0;
},_=function(){
if(c.batchGetQuestionParam)return c.batchGetQuestionParam;
var t={
num:0
};
for(var e in c.data)if(Object.prototype.hasOwnProperty.call(c.data,e)){
var a=e.split("_");
t["__biz"+t.num]=a[0],1===c.data[e].type&&(t["mid"+t.num]=c.data[e].mid,t["idx"+t.num]=c.data[e].idx),
t["type"+t.num]=c.data[e].type,2===c.data[e].type&&(t["topic_id"+t.num]=1),t.num++;
}
return c.batchGetQuestionParam=t,c.batchGetQuestionParam;
},b=function(t){
var e="."+n.classPrefix;
i.on(t.dom,"tap",e+"show_detail_js",function(t){
{
var e=t.delegatedTarget,a=e.getAttribute("data-key"),n=(e.getAttribute("data-miniprogram-appid")||"wx3f84c32dc4b1e06b",
e.getAttribute("data-miniprogram-path")||c.detailPath+"?url="+encodeURIComponent(c.data[a].question_page_url)+"&bizNickname="+encodeURIComponent(c.data[a].biz_nickname));
e.getAttribute("data-miniprogram-title")||"";
}
c.canJumpOnTap?o.jumpUrl({
options:{
userName:c.weapp_username,
scene:1058,
sceneNote:encodeURIComponent(location.href),
relativeURL:o.getRelativeURL(n),
openType:2
},
beforeNonWechatWarn:function(){},
beforeJumpBackupPage:function(){},
onJsapiCallback:function(t){
"openWeApp:ok"===t.err_msg&&window.__addIdKeyReport&&window.__addIdKeyReport("28307",102);
}
}):console.log("cant jumpOnTap");
}),i.on(t.dom,"tap",e+"show_profile_js",function(t){
{
var e=t.delegatedTarget,a=(e.getAttribute("data-key"),e.getAttribute("data-miniprogram-appid")||"wx3f84c32dc4b1e06b",
e.getAttribute("data-miniprogram-path")||c.profilePath+"?biz="+encodeURIComponent(window.biz));
e.getAttribute("data-miniprogram-title")||"";
}
c.canJumpOnTap?o.jumpUrl({
options:{
userName:c.weapp_username,
scene:1058,
sceneNote:encodeURIComponent(location.href),
relativeURL:o.getRelativeURL(a),
openType:2
},
beforeNonWechatWarn:function(){},
beforeJumpBackupPage:function(){},
onJsapiCallback:function(t){
"openWeApp:ok"===t.err_msg&&window.__addIdKeyReport&&window.__addIdKeyReport("28307",102);
}
}):console.log("cant jumpOnTap");
}),i.on(t.dom,"tap",e+"show_theme_js",function(t){
{
var e=t.delegatedTarget,a=e.getAttribute("data-key"),n=(e.getAttribute("data-miniprogram-appid")||"",
e.getAttribute("data-miniprogram-path")||c.topicPath+"?themeId="+encodeURIComponent(c.data[a].themeId)+"&biz="+encodeURIComponent(window.biz));
e.getAttribute("data-miniprogram-title")||"";
}
c.canJumpOnTap?o.jumpUrl({
options:{
userName:c.weapp_username,
scene:1058,
sceneNote:encodeURIComponent(location.href),
relativeURL:o.getRelativeURL(n),
openType:2
},
beforeNonWechatWarn:function(){},
beforeJumpBackupPage:function(){},
onJsapiCallback:function(t){
"openWeApp:ok"===t.err_msg&&window.__addIdKeyReport&&window.__addIdKeyReport("28307",102);
}
}):console.log("cant jumpOnTap");
});
},f=function(t){
c.data[t.key]&&c.data[t.key].invisibleElems&&1*c.data[t.key].dataStatus!==1&&!function(){
var a=t.data||{};
a.dataStatus=c.data[t.key].dataStatus;
var n=c.data[t.key].invisibleElems.map(function(t){
var n=document.createElement("div"),i=r.tmpl(e,a,!0);
return n.innerHTML=i.trim(),t.parentNode.insertBefore(n.firstChild,t.nextsibling);
});
c.data[t.key].invisibleElems=null,n.length>0&&1*c.data[t.key].dataStatus===2&&n.forEach(function(e){
b({
dom:e,
allQuestionImg:t.data.allQuestionImg,
allAnswerImg:t.data.allAnswerImg
});
});
}();
},y=function(){},h=function v(){
a({
url:"/mp/qa?action=batch_get_qa_card",
type:"POST",
dataType:"json",
data:_(),
async:!0,
success:function(t){
t&&t.base_resp&&1*t.base_resp.ret===0&&"[object Array]"===Object.prototype.toString.call(t.qa_card_list)?(t.qa_card_list.forEach(function(e,a){
var i=e.biz_encode+"_"+a;
if(c.data[i]&&c.data[i].invisibleElems){
var o=n.formatQuestionInfo(e,t.svr_time,c.data[i].type);
o.dataKey=i;
var r=c.data[i].type;
c.data[i].qa_id=o.qa_id,1===r&&(c.data[i].biz_nickname=o.biz_nickname,c.data[i].question_page_url=o.question_page_url),
2===r&&(c.data[i].themeId=o.topicId),c.data[i].dataStatus=2,f({
data:o,
key:i
});
}
}),y(4)):y(3);
},
error:function(){
c.retry?(c.retry--,v()):y(3);
}
});
},w=function(){
g()&&h();
};
w();
});define("appmsg/weapp.js",["biz_common/utils/string/html.js","pages/weapp_tpl.html.js","biz_wap/utils/ajax.js","biz_common/dom/event.js","biz_common/tmpl.js","biz_common/dom/class.js","appmsg/weapp_common.js","common/utils.js","biz_wap/utils/mmversion.js","biz_common/base64.js","appmsg/popup_report.js"],function(e){
"use strict";
function t(e,t,n){
var o=new Image;
o.src=("http://mp.weixin.qq.com/mp/jsreport?1=1&key=106&content="+n+",biz:"+biz+",mid:"+mid+",uin:"+uin+"[key1]"+encodeURIComponent(t.toString())+"&r="+Math.random()).substr(0,1024);
}
function n(e,t,n,o,i,p,a){
h({
url:"/mp/appmsgreport?action=appmsg_weapp_report",
data:{
__biz:window.biz||"",
mid:window.mid||"",
idx:window.idx||"",
weapp_appid:e||"",
weapp_pos:t||0,
weapp_title:o||0,
weapp_nickname:n||0,
type:i||0,
scene:window.source||-1,
weapp_type:p,
is_confirm:a||0,
ascene:window.ascene||-1
},
type:"POST",
dataType:"json",
async:!0,
success:function(){}
});
}
function o(e){
var t=e.innerHTML,n=/<img.*src=[\'\"]/,o=/background-image:(\s*)url\(/,i=/background:[^;"']+url\(/;
return n.test(t)||o.test(t)||i.test(t)?!0:!1;
}
function i(e){
var t=e.innerHTML,n=e.style.fontSize;
return 0===t.trim().length||0===parseFloat(n)?!0:!1;
}
function p(){
var e=c("js_content");
if(!e)return!1;
B=e.getElementsByTagName("mp-weapp")||[],x=e.getElementsByTagName("mp-miniprogram")||[],
R=[];
for(var t=e.getElementsByTagName("a"),n=0,o=t.length;o>n;n++){
var i=t[n],p=i.getAttribute("data-miniprogram-appid");
p&&R.push(i);
}
return B.length<=0&&x.length<=0&&0==R.length?!1:K&&0!=K.length?!0:(window.__addIdKeyReport&&window.__addIdKeyReport("27613","52",1),
!1);
}
function a(e){
return e=e||"",e.replace(/&/g,"&amp;").replace(/</g,"&lt;").replace(/>/g,"&gt;").replace(/"/g,"&quot;");
}
function r(e,t,o,i,p){
n(e,t,o,i,4,p),window.__addIdKeyReport&&window.__addIdKeyReport("28307",103);
}
function d(e,t,o,i,p){
n(e,t,o,i,5,p);
}
function s(){
function e(e){
e.preventDefault();
}
function p(e){
e&&(l=setTimeout(function(){
e.style.display="none",c=-1;
},100));
}
window.reportWeappid=[];
for(var s=0;s<K.length;s++)window.reportWeappid.push(K[s].appid);
var m=function(){};
y.on(document.getElementById("js_minipro_dialog_ok"),"click",function(t){
t.stopPropagation(),t.preventDefault(),document.querySelector("body").removeEventListener("touchmove",e);
var n=document.getElementById("js_minipro_dialog");
m&&m(),document.getElementById("js_minipro_dialog").style.display="none",C.report([4,1,"",img_popup?1:0,window.source,n._appid]);
}),y.on(document.getElementById("js_minipro_dialog_cancel"),"click",function(t){
t.stopPropagation(),t.preventDefault(),document.querySelector("body").removeEventListener("touchmove",e);
var o=document.getElementById("js_minipro_dialog");
o.style.display="none",n(o._appid,o._i,o._nickname,o._title,3,1,1),window.__addIdKeyReport&&window.__addIdKeyReport("28307",116),
C.report([3,1,"",img_popup?1:0,window.source,o._appid]);
}),y.on(document.getElementById("js_weapp_without_auth_dialog_ok"),"click",function(){
document.querySelector("body").removeEventListener("touchmove",e),document.getElementById("js_weapp_without_auth_dialog").style.display="none";
});
var l,c,h=!I.canJumpOnTap||I.isNonWechat,E=document.getElementById("js_pc_weapp_code"),B=document.getElementById("js_weapp_without_auth_dialog_mask"),x=document.getElementById("js_pc_weapp_code_img"),R=document.getElementById("js_pc_weapp_code_des");
h&&(y.on(E,"mouseenter",function(){
clearTimeout(l);
}),y.on(E,"mouseleave",function(){
p(E);
})),I.getAppidInfo({
onSuccess:function(T){
console.log("WeappCommon.getAppidInfo onsuccess");
var K=T.data.infoMap;
if(!K)return void(window.__addIdKeyReport&&window.__addIdKeyReport("27613","52",1));
for(s=0;s<z.length;s++)(function(s){
window.__addIdKeyReport("111535",1);
var j=z[s].appid,A=z[s].path,N=z[s].imageUrl,L=z[s].title,S=z[s].elem,M=K[j];
if(!M)return void(window.__addIdKeyReport&&window.__addIdKeyReport("27613","52",1));
var W=S.tagName.toLowerCase(),P=S.firstChild&&1==S.firstChild.nodeType&&"IMG"===S.firstChild.tagName;
if(P=P||S.firstElementChild&&"IMG"===S.firstElementChild.tagName,"a"!=W)S.innerHTML=v.tmpl(w,{
imageUrl:a(N),
title:a(L),
nickname:a(M.nickname),
avatar:a(M.logo_url)
});else{
if(P){
var U=S.firstChild;
U&&b.addClass(S,"weapp_image_link");
}else b.addClass(S,"weapp_text_link");
S.setAttribute("href","");
}
if(T.resp&&T.resp.weapp_info&&T.resp.weapp_info.length)for(var H=0;H<T.resp.weapp_info.length;H++)if(T.resp.weapp_info[H].weapp_appid===j&&1===T.resp.weapp_info[H].has_guarantee_flag){
b.addClass(S.getElementsByClassName("guarantee_icon")[0],"show");
break;
}
y.on(S,"tap",function(){
if(m=function(){
var e=P?1:"a"==W?2:0;
return I.jumpUrl({
sceneNote:encodeURIComponent(location.href),
appid:j,
path:A,
scene:window.__weapp_scene__||1058,
beforeNonWechatWarn:function(){
d(j,s,M.nickname,L,e);
},
beforeJumpBackupPage:function(){
r(j,s,M.nickname,L,e);
},
onJsapiCallback:function(e){
"openWeApp:ok"===e.err_msg&&window.__addIdKeyReport&&window.__addIdKeyReport("28307",102),
t(107,new Error(e.err_msg),"");
}
}),window.__addIdKeyReport&&window.__addIdKeyReport("28307",100),n(j,s,M.nickname,L,3,e,P?2:0),
P&&window.__addIdKeyReport&&window.__addIdKeyReport("28307",115),!1;
},k.isInMiniProgram&&-1===q.indexOf(j)&&k.gtVersion("7.0.5",!0)){
var p=document.getElementById("js_weapp_without_auth_dialog");
return p.style.display="block",document.querySelector("body").addEventListener("touchmove",e,{
passive:!1
}),document.getElementById("js_weapp_without_auth_weappurl").src="",I.getAppidCode({
appid:j,
path:A
},function(e){
document.getElementById("js_weapp_without_auth_weappurl").src=e;
}),!1;
}
if(P&&C.report([2,1,"",img_popup?1:0,window.source,j]),(P||b.hasClass(S,"weapp_text_link")&&(o(S)||i(S)))&&img_popup){
document.getElementById("js_minipro_dialog_head").innerText="即将打开小程序",document.getElementById("js_minipro_dialog_body").innerText=M.nickname;
var p=document.getElementById("js_minipro_dialog");
return p.style.display="block",document.querySelector("body").addEventListener("touchmove",e,{
passive:!1
}),p._appid=j,p._i=s,p._nickname=M.nickname,p._title=L,n(j,s,M.nickname,L,3,1,0),
I.canJumpOnTap&&window.__addIdKeyReport&&window.__addIdKeyReport("28307",114),!1;
}
return m();
},"a"==W),y.on(S,"click",function(e){
e.preventDefault(),e.stopPropagation();
},"a"==W),h&&(y.on(S,"mouseenter",function(){
function e(e){
function t(){
if(!l&&c===s){
E.style.display="block",l=!0;
var e=E.offsetHeight,t=E.offsetWidth;
"a"!=W||P?n>t?(g(E,"right-center"),E.style.left=n-t-m+"px",E.style.top=o+"px"):(g(E),
E.style.top=o+d-e-m+"px",E.style.left=n+r-t-m+"px"):(E.style.left=i>n+r/2-t/2?i+"px":n+r/2+t/2>i+p?i+p-t+"px":n+r/2-t/2+"px",
a>e?(g(E,"down-center"),E.style.top=o-e-m+"px"):(g(E,"up-center"),E.style.top=o+d-m+"px"));
}
}
if(e){
var n=u(S),o=_(P?S.firstElementChild:S),i=u(S.parentNode),p=S.parentNode.offsetWidth,a=S.getBoundingClientRect().top,r=P?S.firstElementChild.offsetWidth:S.offsetWidth,d=P?S.firstElementChild.offsetHeight:S.offsetHeight,m=8,l=!1;
R.innerText=f(M.nickname,48),x.onload=t,x.src=e,(x.complete||x.width)&&t();
}
}
clearTimeout(l),c!==s&&(E.style.display="none",c=s,I.getAppidCode({
appid:j,
path:A
},e));
}),y.on(S,"mouseleave",function(){
p(E);
})),k.isInMiniProgram&&-1===q.indexOf(j)&&k.gtVersion("7.0.5",!0)&&y.on(B,"click",function(){
var t=document.getElementById("js_weapp_without_auth_dialog");
document.querySelector("body").removeEventListener("touchmove",e),t.style.display="none";
});
})(s);
var N=null,L=function(){
N=null;
for(var e=0;e<A.length;e++){
var t=A[e].elem,o=t.tagName.toLowerCase(),i=t.firstChild&&1==t.firstChild.nodeType,p=i?1:"a"==o?2:0,a=A[e].elem.getBoundingClientRect();
if(a.top<j.getInnerHeight()&&a.bottom>0){
setTimeout(function(){
window.__addIdKeyReport&&window.__addIdKeyReport("28307",101);
},0);
var r=A[e].appid;
r&&K[r]&&K[r].nickname&&n(r,e,K[r].nickname,A[e].title,2,p),A.splice(e--,1);
}
}
};
L(),y.on(window,"scroll",function(){
N||(N=setTimeout(L,100));
});
},
onError:function(e){
3==e.code&&t(106,e.catchErr,"parsing weapp info error");
}
});
}
function m(){
for(var e=0,t=0;t<x.length+B.length;t++){
var n=t<x.length,o=n?x[t]:B[t-x.length],i=o.getAttribute(n?"data-miniprogram-appid":"data-weapp-appid")||"",p=o.getAttribute(n?"data-miniprogram-path":"data-weapp-path")||"",a=o.getAttribute(n?"data-miniprogram-imageUrl":"data-weapp-imageUrl")||"",r=o.getAttribute(n?"data-miniprogram-title":"data-weapp-title")||"",d=document.createElement("span");
o.setAttribute("class",""),d.setAttribute("class","weapp_display_element js_weapp_display_element"),
z.push({
appid:i,
path:p,
imageUrl:a,
title:r,
elem:d
}),A.push({
appid:i,
elem:d,
title:r
}),o.parentNode.insertBefore(d,o.nextSibling),l(a)||e++;
}
for(var t=0;t<R.length;t++){
var s=R[t];
z.push({
appid:s.getAttribute("data-miniprogram-appid"),
path:s.getAttribute("data-miniprogram-path")||"",
elem:s
});
}
e>0&&setTimeout(function(){
(new Image).src="//mp.weixin.qq.com/mp/jsmonitor?idkey=64469_33_"+e+"&t="+Math.random();
},0);
}
function l(e){
for(var t,n=[/^http(s)?:\/\/mmbiz\.qpic\.cn([\/?].*)*$/i,/^http(s)?:\/\/mmbiz\.qlogo\.cn([\/?].*)*$/i,/^http(s)?:\/\/mmsns\.qpic\.cn([\/?].*)*$/i],o=0;t=n[o++];)if(t.test(e))return!0;
return!1;
}
function c(e){
return document.getElementById(e);
}
function u(e){
for(var t=0;e;)t+=e.offsetLeft,e=e.offsetParent;
return t;
}
function _(e){
for(var t=0;e;)t+=e.offsetTop,e=e.offsetParent;
return t;
}
function g(e,t){
for(var n=0;3>n;n++)b.removeClass(e,"weui-desktop-popover_pos-up-"+N[n]),b.removeClass(e,"weui-desktop-popover_pos-down-"+N[n]),
b.removeClass(e,"weui-desktop-popover_pos-left-"+L[n]),b.removeClass(e,"weui-desktop-popover_pos-right-"+L[n]);
b.removeClass(e,"weui-desktop-popover_hide-arrow"),t?b.addClass(e,"weui-desktop-popover_pos-"+t):b.addClass(e,"weui-desktop-popover_hide-arrow");
}
function f(e,t){
var n=/[^\x00-\xff]/g;
if(e.replace(n,"**").length>t)for(var o=Math.floor(t/2),i=o,p=e.length;p>i;i++)if(e.substring(0,i).replace(n,"**").length>=t)return e.substring(0,i)+"...";
return e;
}
e("biz_common/utils/string/html.js");
var w=e("pages/weapp_tpl.html.js"),h=e("biz_wap/utils/ajax.js"),y=e("biz_common/dom/event.js"),v=e("biz_common/tmpl.js"),b=e("biz_common/dom/class.js"),I=e("appmsg/weapp_common.js"),j=e("common/utils.js"),k=e("biz_wap/utils/mmversion.js"),E=e("biz_common/base64.js"),C=e("appmsg/popup_report.js"),B=null,x=null,R=null,T={},z=[],K=I.appidSnInfo,A=[],q=E.fromBase64(appid_list).split(",");
if(p()){
m(),s();
var N=["left","center","right"],L=["top","center","bottom"];
return T;
}
});