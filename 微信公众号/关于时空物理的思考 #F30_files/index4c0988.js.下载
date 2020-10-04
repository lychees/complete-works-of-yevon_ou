define("biz_wap/ui/weui.js",[],function(){
"use strict";
function e(){
for(var e=document.getElementsByTagName("link"),i=/^http(s)?:\/\/res\.wx\.qq\.com\/open\/libs\/weui\/([^\/]*)\/weui(\.min)?\.css$/,n=0;n<e.length;n++){
var t=(e[n].href.match(i)||[])[2];
if(t){
if("1"===t[0])return!0;
console.warn("Weui.css("+t+") in page is deprecated. Weui.css(1.0+) will be insert in page automatically.");
}
}
return!1;
}
function i(){
var e=["actionSheet","alert","confirm","dialog","validate","checkIfBlur","gallery","loading","picker","datePicker","searchBar","slider","tab","toast","topTips","uploader"];
window.weui={};
for(var i=0;i<e.length;i++)!function(i){
window.weui[e[i]]=function(){
a.push({
name:e[i],
args:arguments
}),console.info(e[i]+" will be executed after weui.js loaded.");
};
}(i);
}
function n(){
var e=document.createElement("script");
e.onload=function(){
for(var e=0;e<a.length;e++)window.weui[a[e].name].apply(window,a[e].args);
},e.onerror=function(){
throw new Error("weui.js loaded fail.");
},e.src=r,document.body.appendChild(e);
}
var t="https://res.wx.qq.com/open/libs/weui/2.1.3/weui.min.css",r="https://res.wx.qq.com/open/libs/weuijs/1.2.1/weui.min.js",a=[];
if(!e()){
var o=document.createElement("link");
o.href=t,o.rel="stylesheet",document.head.appendChild(o);
}
i(),n();
});function _typeof(e){
return e&&"undefined"!=typeof Symbol&&e.constructor===Symbol?"symbol":typeof e;
}
define("appmsg/index.js",["biz_wap/ui/weui.js","appmsg/set_font_size.js","biz_common/tmpl.js","cps/tpl/banner_tpl.html.js","cps/tpl/card_tpl.html.js","cps/tpl/list_tpl.html.js","biz_common/utils/string/html.js","appmsg/weapp_common.js","biz_wap/utils/device.js","biz_common/dom/class.js","appmsg/log.js","biz_wap/utils/ajax.js","biz_common/dom/attr.js","appmsg/max_age.js","biz_wap/utils/mmversion.js","appmsg/test.js","biz_common/dom/event.js","biz_wap/jsapi/core.js","biz_common/moment.js","appmsg/appmsg_report.js","biz_common/utils/url/parse.js","a/mpAdAsync.js","biz_wap/utils/wapsdk.js","common/utils.js","complain/localstorage.js","appmsg/popup_report.js","appmsg/pay_report_utils.js","appmsg/loading.js","appmsg/finance_communicate.js","common/comm_report.js","page/appmsg_new/combo.css","page/appmsg_new/not_in_mm.css","appmsg/cdn_img_lib.js","appmsg/share.js","biz_common/log/jserr.js","biz_wap/ui/lazyload_img.js","appmsg/async.js","appmsg/copyright_report.js","appmsg/outer_link.js","appmsg/review_image.js","appmsg/product.js","appmsg/page_pos.js","appmsg/iframe.js","appmsg/qqmusic.js","appmsg/voice.js","redpackage/redpacketcover.js","appmsg/autoread.js","appmsg/voicemsg.js","appmsg/weproduct.js","appmsg/weapp.js","question_answer/appmsg.js","appmsg/wxtopic.js","appmsg/cdn_speed_report.js","appmsg/appmsg_copy_report.js","appmsg/report_and_source.js","appmsg/report.js","appmsg/fereport_without_localstorage.js","appmsg/fereport.js","biz_wap/safe/mutation_observer_report.js","sougou/index.js"],function(e){
"use strict";
function t(e){
for(var t=window.location.search,o=t.substring(1,t.length).split("&"),i=0;i<o.length;i++){
var n=o[i].split("=");
if(n[0].toUpperCase()===e.toUpperCase())return n[1];
}
return"";
}
function o(){
function o(e){
if(e&&0!=e.length){
for(var t={
batch_no:A.getQuery("batch_no")||"",
bizuin:window.biz||"",
biz:window.biz||"",
mid:window.mid||"",
idx:window.idx||"",
total:e.length
},o=0;o<e.length;o++){
var i=e[o],n=o+1;
for(var r in i)i.hasOwnProperty(r)&&(t[r+""+n]=i[r]);
}
l({
url:"/mp/productreport?",
type:"POST",
data:t,
dataType:"json",
async:!0
});
}
}
function q(){
X&&clearTimeout(X),X=setTimeout(function(){
try{
X=null;
for(var e=0;e<F.length;e++){
var t=F[e],i=w.attr(t,"data-showed");
if("no"==i){
var n=t.getElementsByClassName("js_product_loop_content");
if(n.length>0){
n=n[0];
var r=n.getBoundingClientRect(),a=r.height||r.bottom-r.top;
if(a>0&&r.top<x.getInnerHeight()&&r.bottom>0){
t.setAttribute("data-showed","yes");
var d=n.getAttribute("data-pid");
d&&o([{
wxa_appid:n.getAttribute("data-wxaappid"),
pid:d,
type:3,
absolute_order:e+1,
appid:n.getAttribute("data-appid")||"",
templateid:n.getAttribute("data-templateid")||"",
relative_order:1*n.getAttribute("data-order"),
packid:n.getAttribute("data-packid")||""
}]);
}
}
}
}
}catch(s){}
},100);
}
function O(e){
try{
for(var c=window.pageYOffset||document.documentElement.scrollTop,m=0;m<F.length;m+=N){
var g=F[m];
if(!(g.offsetTop>c+x.getInnerHeight()+100)){
var u=w.attr(g,"data-cpsstatus");
if("hide"==u){
g.setAttribute("data-cpsstatus","loading");
for(var f=""+m,y=1,v=m+1;v<F.length&&m+N>v;v++)f=f+"%2c"+v,y++;
var b=Math.ceil(1e7*Math.random());
if(""!==t("mockcps"))var A="/mp/cps_product_info?biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&cpslist="+f+"&sn="+window.sn+"&mockcps="+t("mockcps");else var A="/mp/cps_product_info?biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&cpslist="+f+"&sn="+window.sn+"&istempurl="+(window.is_temp_url||0)+"&random="+b;
!function(e,t,c){
l({
url:t,
type:"GET",
dataType:"json",
async:!0,
error:function(){
try{
window.__addIdKeyReport("64469","18",c);
}catch(e){}
},
success:function(e){
try{
window.__addIdKeyReport("64469","16",e.product_list.length),e.product_list.length<c&&window.__addIdKeyReport("64469","18",c-e.product_list.length);
for(var t=0;t<e.product_list.length;t++){
e.product_list[t].data.cps_isready=!0,e.product_list[t].data.pid_type=e.product_list[t].data.pid_type||e.product_list[t].attr.pid_type;
var m=F[e.product_list[t].index],l=e.product_list[t].template_id;
"list"==l?m.innerHTML=n.tmpl(d,e.product_list[t].data):"banner"==l?m.innerHTML=n.tmpl(r,e.product_list[t].data):"card"==l&&(m.innerHTML=n.tmpl(a,e.product_list[t].data)),
e.product_list[t].weapp_username&&(e.product_list[t].attr.weapp_username=e.product_list[t].weapp_username),
e.product_list[t].weapp_version&&(e.product_list[t].attr.weapp_version=e.product_list[t].weapp_version),
m.setAttribute("data-cpsstatus","complete");
for(var g=m.getElementsByClassName("js_product_loop_content"),u=0;u<g.length;u++)for(var f in e.product_list[t].attr)g[u].setAttribute("data-"+f,e.product_list[t].attr[f]);
for(var y=m.getElementsByTagName("img"),u=0;u<y.length;u++)y[u].src=w.attr(y[u],"data-src");
!function(e,t){
if(h.on(e,"tap",".js_product_loop_content",function(e){
try{
var i=e.delegatedTarget,n=i.getAttribute("data-wxaappid"),r=i.getAttribute("data-wxapath"),a=i.getAttribute("data-pid"),d=i.getAttribute("data-appid"),p=i.getAttribute("data-cpspackage"),c=Math.floor((new Date).getTime()/1e3)+5184e3,m=i.getAttribute("data-weapp_username"),l=i.getAttribute("data-weapp_version");
s.jumpUrl({
cps_weapp_username:m,
cps_weapp_version:l,
privateExtraData:{
cookies:"cps_package="+encodeURIComponent(p)+"; expires="+c+"; busid=mmbiz_ad_cps; domain=*; spread=*"
},
sourceAppId:d,
appid:n,
path:r,
scene:1091,
sceneNote:encodeURIComponent(location.href)+":"+encodeURIComponent(a),
beforeNonWechatWarn:function(){},
beforeJumpBackupPage:function(){},
onJsapiCallback:function(e){
"openWeApp:ok"===e.err_msg&&a&&o([{
wxa_appid:n,
pid:a,
type:4,
absolute_order:t+1,
appid:i.getAttribute("data-appid")||"",
templateid:i.getAttribute("data-templateid")||"",
relative_order:1*i.getAttribute("data-order"),
packid:i.getAttribute("data-packid")||""
}]);
}
});
}catch(e){}
return!1;
}),_.isIOS&&location.href.match(/fontScale=\d+/)&&p.os.ipad&&p.os.getNumVersion()>=13){
var n=location.href.match(/fontScale=(\d+)/);
i(e,parseFloat(n[1])/100);
}
}(m,e.product_list[t].index);
}
q();
}catch(v){
window.__addIdKeyReport("64469","18",e.product_list.length);
}
}
});
}(f,A,y);
}
}
}
}catch(e){
console.log(e);
}
}
function L(e){
try{
$&&clearTimeout($),$=setTimeout(function(){
O(e);
},300);
}catch(e){}
}
function K(){
var e=document.documentElement.scrollTop||window.pageYOffset||document.body.scrollTop;
if(e>=40&&!V)if(V=!0,M){
if(y.invoke("currentMpInfoShow",{
userName:window.user_name,
brandName:D
},function(){}),!W){
var t={
BizUin:biz,
AppMsgID:1*mid,
ItemIndex:1*idx,
Scene:1*source,
SubScene:1*subscene,
EnterId:13===enterid.toString().length?Math.floor(enterid/1e3):1*enterid,
SessionId:sessionid+"",
Event:1,
CurrScreen:0,
ItemShowType:1*window.item_show_type,
ExitHeight:0
};
B.report(17335,t),W=!0;
}
}else document.title=window.title;else 40>e&&V&&(V=!1,M?y.invoke("currentMpInfoHide",function(){}):document.title="");
}
function H(e,t){
var o={
lossy:"UklGRiIAAABXRUJQVlA4IBYAAAAwAQCdASoBAAEADsD+JaQAA3AAAAAA",
lossless:"UklGRhoAAABXRUJQVlA4TA0AAAAvAAAAEAcQERGIiP4HAA==",
alpha:"UklGRkoAAABXRUJQVlA4WAoAAAAQAAAAAAAAAAAAQUxQSAwAAAARBxAR/Q9ERP8DAABWUDggGAAAABQBAJ0BKgEAAQAAAP4AAA3AAP7mtQAAAA==",
animation:"UklGRlIAAABXRUJQVlA4WAoAAAASAAAAAAAAAAAAQU5JTQYAAAD/////AABBTk1GJgAAAAAAAAAAAAAAAAAAAGQAAABWUDhMDQAAAC8AAAAQBxAREYiI/gcA"
},i=new Image;
i.onload=function(){
var o=i.width>0&&i.height>0;
t(e,o);
},i.onerror=function(){
t(e,!1);
},i.src="data:image/webp;base64,"+o[e];
}
function U(){
var e=window.performance||window.msPerformance||window.webkitPerformance;
if(e.timing){
var t=e.timing;
m("[Appmsg] dns:"+(t.domainLookupEnd-t.domainLookupStart)+"^^^ ssl:"+(0==t.secureConnectionStart?0:t.connectEnd-t.secureConnectionStart)+"^^^ tcp:"+(t.connectEnd-t.connectStart)+"^^^ request:"+(t.responseStart-t.requestStart)+"^^^ getPackageTime:"+(t.responseEnd-t.responseStart)+"^^^ domCententLoaded:"+(t.domContentLoadedEventStart-t.domLoading)+"^^^ domComplete:"+(t.domComplete-t.domLoading)+"^^^ firstViewTime:"+(real_show_page_time-t.navigationStart)+"^^^ interactiveTime:"+(page_endtime-t.navigationStart))+"^^^ ua:"+window.navigator.userAgent,
setTimeout(function(){
t.loadEventEnd&&m("[Appmsg] onload:"+(t.loadEventEnd-t.loadEventStart));
},100);
}
"function"!=typeof String.prototype.trim&&(String.prototype.trim=function(){
return this.replace(/^\s+|\s+$/g,"");
}),""==document.getElementById("js_content").innerHTML.trim()&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=24729_94_1");
var o=Math.random();
.001>o&&document.getElementById("js_read_area3")&&document.getElementById("js_read_area3").innerText&&document.getElementById("js_read_area3").innerText.indexOf("Pageview")>-1&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=24729_95_1"),
window.__wxjs_is_wkwebview&&window.__addIdKeyReport("28307",67);
}
try{
var F=document.getElementsByTagName("mpcps");
window.__addIdKeyReport("64469","15",F.length);
for(var Q=0;Q<F.length;Q++){
F[Q].setAttribute("data-cpsstatus","hide"),F[Q].setAttribute("data-showed","no");
var G={
cps_isready:!1,
cps_state:"",
pid_type:"",
img_url:"",
title:"",
desc:"",
source_name:"",
source_logo_url:"",
is_ad:1
},Y=w.attr(F[Q],"data-templateid");
"list"==Y?F[Q].innerHTML=n.tmpl(d,G):"banner"==Y?F[Q].innerHTML=n.tmpl(r,G):"card"==Y&&(F[Q].innerHTML=n.tmpl(a,G));
}
}catch(J){
console.log(J);
}
var $,X=null;
q(),h.on(window,"scroll",q),O(),h.on(window,"scroll",L),y.on("topbar:click",function(){
var e={
BizUin:biz,
AppMsgID:1*mid,
ItemIndex:1*idx,
Scene:1*source,
SubScene:1*subscene,
EnterId:13===enterid.toString().length?Math.floor(enterid/1e3):1*enterid,
SessionId:sessionid+"",
Event:3,
CurrScreen:Math.ceil((window.pageYOffset||document.documentElement.scrollTop)/x.getInnerHeight()),
ItemShowType:1*window.item_show_type,
ExitHeight:1*((window.pageYOffset||document.documentElement.scrollTop)+x.getInnerHeight())
};
B.report(17335,e);
}),window.is_new_msg&&-1!=navigator.userAgent.indexOf("MicroMessenger")&&(window.title&&(window.title=window.title.replace(/&#39;/g,"'").replace(/&nbsp;/g," ").replace(/&lt;/g,"<").replace(/&gt;/g,">").replace(/&quot;/g,'"').replace(/&amp;/g,"&")),
window.msg_title&&(window.msg_title=window.msg_title.replace(/&#39;/g,"'").replace(/&nbsp;/g," ").replace(/&lt;/g,"<").replace(/&gt;/g,">").replace(/&quot;/g,'"').replace(/&amp;/g,"&")),
hd_head_img||j.jsmonitor({
id:115849,
key:26,
value:1
}),y.invoke("currentMpInfo",{
userName:window.user_name,
brandName:D,
title:window.msg_title||"",
brandIcon:hd_head_img.replace(/\/0$/,"/132"),
itemShowType:window.item_show_type,
isPaySubscribe:window.isPaySubscribe,
topBarStyle:M?1:0,
topBarShowed:!1,
isMenuShowBrandInfo:1
},function(){}),y.invoke("createWebViewForFastLoad",{
scene:1
},function(e){
console.log(e);
}),h.on(window,"load",K),h.on(window,"scroll",K));
var Z=document.getElementsByTagName("body");
if(!Z||!Z[0])return!1;
Z=Z[0],_.isInMiniProgram&&(document.getElementById("js_name")&&c.addClass(document.getElementById("js_name"),"tips_global_primary"),
document.getElementsByClassName("account_nickname_inner").length&&c.addClass(document.getElementsByClassName("account_nickname_inner")[0],"tips_global_primary"),
document.getElementById("js_share_author")&&c.addClass(document.getElementById("js_share_author"),"tips_global_primary")),
function(){
function e(){
if(i.length)for(var e=document.documentElement.scrollTop||document.body.scrollTop,t=0;t<i.length;t++)if(1!=i[t].getAttribute("hasload")){
var o=i[t].getBoundingClientRect();
(o.top<s+e&&o.top>e||o.top+o.height>e&&o.top+o.height<s+e)&&i[t].getAttribute("href").length>0&&(i[t].setAttribute("hasload",1),
y.invoke("downloadPageDataForFastLoad",{
itemList:[{
item_show_type:i[t].getAttribute("data-itemshowtype"),
url:i[t].getAttribute("href")
}]
},function(e){
console.log(e);
}),i.splice(t,1),t--);
}
}
function t(){
for(var e=0;e<a.length;e++){
var t=a[e],o=t.getBoundingClientRect();
(o.top<=0&&o.top+o.height>=0||o.top>0&&o.top<s)&&(a.splice(e,1),e--,k.report([1,k.getRedirectType(t.parentNode.getAttribute("href")),"",img_popup?1:0,window.source,k.getUrlData(t.parentNode.getAttribute("href"))]));
}
for(var e=0;e<d.length;e++){
var t=d[e],o=t.getBoundingClientRect();
(o.top<=0&&o.top+o.height>=0||o.top>0&&o.top<s)&&(d.splice(e,1),e--,k.report([1,1,"",img_popup?1:0,window.source,t.getAttribute("data-miniprogram-appid")]));
}
}
function o(){
e(),t();
}
for(var i=[],n=document.getElementById("js_content").getElementsByTagName("a"),r=0;r<n.length;r++)null!==n[r].getAttribute("data-itemshowtype")&&i.push(n[r]);
var a=[];
Array.prototype.map.call(document.getElementById("js_content").getElementsByClassName("h5_image_link"),function(e){
e.parentNode.getAttribute("href")&&e.parentNode.getAttribute("href").length>0&&a.push(e);
});
var d=[];
Array.prototype.map.call(document.getElementById("js_content").getElementsByClassName("weapp_image_link"),function(e){
d.push(e);
});
var s=window.innerHeight||document.documentElement.clientHeight;
h.on(window,"scroll",o),o();
}(),function(){
window.isPaySubscribe&&(y.on("onScreenShot",function(){
E.reportPayAppmsg(6);
}),window.isPaid||!function(){
var e="isPaid-"+window.biz+"-"+window.mid+"-"+window.idx,t=document.getElementById("js_pay_panel"),o=t.getElementsByClassName("js_pay_btn")[0],i=document.getElementById("js_pay_panel_bottom"),n=window.getComputedStyle(i),r=40+parseInt(n.paddingTop,10)+parseInt(n.paddingBottom,10),a=_.isWindows||_.isMac&&!_.isIOS,d=_.isGooglePlay;
if(_.isAndroid&&(y.invoke("handleMPPageAction",{
action:"isGPVersion"
},function(e){
console.log("GPVersion",e),e.err_msg.indexOf("ok")>-1&&(d=1*e.GPVersion);
}),"1"===window.localStorage.getItem(e)&&E.report110809(30)),a)for(var s=document.getElementsByClassName("js_pay_qrcode"),p="/mp/paysubqrcode?action=get_article_qrcode&__biz="+window.biz+"&mid="+window.mid+"&idx="+window.idx+"&sn="+window.sn+"#wechat_redirect",m=0,w=s.length;w>m;m++)s[m].src=p;
_.isInMiniProgram&&(c.addClass(o,"btn_disabled"),c.addClass(i.getElementsByClassName("js_pay_btn")[0],"btn_disabled")),
_.isIOS&&window.payShowIAPPrice&&!function(){
var e=setTimeout(function(){
e=null,console.log("getIAPProductInfo timeout"),E.reportOverseaPay("",0,1,0,"",2,"");
},3e3),t=Date.now();
y.invoke("handleMPPageAction",{
action:"getIAPProductInfo",
productId:window.payProductId
},function(o){
if("number"==typeof e){
clearTimeout(e);
var i=Date.now()-t;
if(console.log("getIAPProductInfo",o,i+"ms"),-1!==o.err_msg.indexOf(":ok")){
if(E.report110809(38),window.payProductId!==o.productId)return void E.report110809(44);
window.oriProductFee?("CNY"!==o.currencyCode&&E.report110809(40),E.reportOverseaPay(o.currencyCode,100*o.price.toFixed(2),1,i,o.countryCode,0,o.err_msg+(o.err_desc?"__"+o.err_desc:""))):(window.IAPProductInfo=o,
window.IAPProductInfo.invokeTime=i);
}else E.report110809(39),E.reportOverseaPay("",0,1,0,"",1,o.err_msg+(o.err_desc?"__"+o.err_desc:""));
}
});
}(),window.jump2pay&&h.on(window,"load",function(){
window.scrollTo(0,t.getBoundingClientRect().top-x.getInnerHeight()/3);
});
var g=function(){
var e=o.getBoundingClientRect().top;
if(e+r>window.innerHeight){
if(1*window.previewPercent===0)return;
i.className="pay pay__notice pay__notice_show";
}else i.className="pay pay__notice",window.is_finished_preview=1;
};
g(),h.on(window,"scroll",g);
var u=!1,f=function v(t,o){
if(E.report110809ForDevice(32),!_.isInMiniProgram){
if(d)return void window.weui.alert("暂不支持Google Play支付，将微信更新为中国版微信后，可正常付费");
if(!o){
if(!a&&u)return;
if(!_.isWechat&&!a)return void window.weui.alert("请在微信内进行付费");
u=!0;
}
var i=t.currentTarget;
if(!a&&1*i.dataset.ready===0)return!o&&S.show("生成订单中"),setTimeout(v,100,{
currentTarget:i
},!0);
if(E.reportPayAppmsg(9),window.is_temp_url)window.weui.alert("临时链接无需付费，请谨慎分享，避免内容泄露",function(){
u=!1,location.replace(location.href+"&temp_is_paid=1");
});else if(a){
var n=function(){
var e="js_pay_qrcode_wrap",t=i.nextElementSibling;
if("block"===t.style.display)return{
v:void 0
};
i.classList.contains("js_article_bottom")&&t.classList[i.getBoundingClientRect().top<300?"add":"remove"]("pay__notice-qrcode_bottom");
var o=function n(o){
if("none"!==t.style.display){
for(var r=o.target;!(null===r||r.classList&&r.classList.contains(e)||r===i);)r=r.parentNode;
r!==i&&(null!==r&&r.classList.contains(e)||(t.style.display="none",h.off(window,"click",n)));
}
};
h.on(window,"click",o),t.style.display="block";
}();
if("object"===("undefined"==typeof n?"undefined":_typeof(n)))return n.v;
}else{
var r=function(){
if(_.isIOS&&_.ltVersion("7.0.10")||_.isAndroid&&_.ltVersion("7.0.10"))return location.replace("https://support.weixin.qq.com/cgi-bin/mmsupport-bin/readtemplate?t=page/common_page__upgrade&btn_text=btn_text_0&text=text000"),
{
v:void 0
};
_.isAndroid&&"1"===window.localStorage.getItem(e)&&E.report110809(31),E.report110809ForDevice(34);
var t=function(){
E.reportPayAppmsg(1),y.invoke("handleMPPageAction",{
action:"paySuccess",
fullUrl:window.location.href,
itemShowType:item_show_type
},function(t){
u=!1,E.report110809(t.err_msg.indexOf("ok")>-1?19:20),window.localStorage&&window.localStorage.setItem&&window.localStorage.setItem(e,"1"),
window.__second_open__?window.location.href=window.location.href+"&r="+Math.random()+"#wechat_redirect":window.location.reload();
});
};
S.show("生成订单中"),l({
url:"/mp/paysub?action=create_order",
type:"POST",
dataType:"json",
data:{
__biz:window.biz,
mid:window.mid,
idx:window.idx,
sn:window.sn,
version:window.clientversion.htmlDecode(),
is_from_pc:window.jump2pay
},
async:!0,
success:function(e){
if(e&&e.base_resp&&0===e.base_resp.ret)!function(){
E.report110809(13),E.report110809ForDevice(36);
var o=Math.round(new Date/1e3);
if(_.isIOS){
var i=e.iap_info;
y.invoke("requestVirtualPayment",{
appID:i.appid,
priceLevel:i.price_level,
busiType:23,
busiId:i.busi_id,
productDesc:i.desc,
sign:i.sign,
extInfo:i.ext_info
},function(i){
console.log("requestVirtualPayment res: ",i),i.err_msg.indexOf("ok")>-1?(E.report110809(15),
E.reportPay(o,1,e.order_id),t()):i.err_msg.indexOf("cancel")>-1?(u=!1,E.report110809(28),
E.reportPay(o,2,e.order_id),console.log("pay cancel")):i.err_msg.indexOf("fail")>-1?(u=!1,
E.report110809(16),E.reportPay(o,3,e.order_id,i.err_msg,i.err_code,i.err_domain),
window.weui.alert(i.err_msg.slice(i.err_msg.indexOf("fail")+4))):(u=!1,window.weui.alert(i.err_msg));
}),window.payShowIAPPrice&&!function(){
var e=setTimeout(function(){
e=null,console.log("getIAPProductInfo timeout"),E.reportOverseaPay("",0,2,0,"",2,"");
},3e3),t=Date.now();
y.invoke("handleMPPageAction",{
action:"getIAPProductInfo",
productId:window.payProductId
},function(o){
if("number"==typeof e){
clearTimeout(e);
var i=Date.now()-t;
if(console.log("getIAPProductInfo",o,i+"ms"),-1!==o.err_msg.indexOf(":ok")){
if(E.report110809(41),window.payProductId!==o.productId)return void E.report110809(44);
window.IAPProductInfo?window.IAPProductInfo.currencySymbol!==o.currencySymbol&&E.report110809(43):window.oriProductFee&&"￥"!==o.currencySymbol&&E.report110809(43),
E.reportOverseaPay(o.currencyCode,100*o.price.toFixed(2),2,i,o.countryCode,0,o.err_msg+(o.err_desc?"__"+o.err_desc:""));
}else E.report110809(42),E.reportOverseaPay("",0,2,0,"",1,o.err_msg+(o.err_desc?"__"+o.err_desc:""));
}
});
}();
}else{
var n=e.midas_info;
window.h5sdk.directPay({
sandbox:!!n.sandbox,
ontimeout:function(){
u=!1,window.weui.alert("支付超时，请稍后重试");
},
methods:{
onPayEnd:function(i,n){
console.log("directPay res: ",i,n),1===i?(E.report110809(17),E.reportPay(o,1,e.order_id,n,i),
t()):-1===i&&/:cancel$/.test(n)?(u=!1,E.report110809(29),E.reportPay(o,2,e.order_id,n,i),
console.log("pay cancel")):(u=!1,E.report110809(18),E.reportPay(o,3,e.order_id,n,i),
window.weui.alert("支付失败，请稍后重试"));
}
}
},{
pf:n.pf,
appid:n.appid,
type:"goods",
openid:n.openid,
extend:{
hideOfferName:1
},
goodstokenurl:n.url_params,
usewxappid:"1",
wx_h5pay:0,
direct_pay_channel:"wechat"
});
}
}();else switch(u=!1,e&&e.base_resp&&e.base_resp.ret){
case 202600:
window.weui.alert("文章已被删除");
break;

case 202601:
window.weui.alert("由于文章被取消原创，不可付费阅读");
break;

case 202602:
window.weui.alert("你已购买过该文章，无需重复购买",t);
break;

case 202604:
window.weui.alert("此内容违规已被封禁，不支持付费");
break;

case 202607:
window.weui.alert("暂不支持Google Play支付，将微信更新为中国版微信后，可正常付费");
break;

case 202608:
location.replace("https://support.weixin.qq.com/cgi-bin/mmsupport-bin/readtemplate?t=page/common_page__upgrade&btn_text=btn_text_0&text=text000");
break;

case 202609:
window.weui.alert("你已成为该公众号的黑名单用户，暂时无法付费");
break;

case 202612:
window.weui.alert("此帐号付费功能已被封禁，不支持付费");
break;

default:
E.report110809(14),window.weui.alert("订单创建失败，请稍后重试");
}
},
error:function(){
u=!1,window.weui.alert("系统错误，请稍后重试");
},
complete:function(){
S.hide();
}
});
}();
if("object"===("undefined"==typeof r?"undefined":_typeof(r)))return r.v;
}
}
};
h.tap(o,f),h.tap(i.getElementsByClassName("js_pay_btn")[0],f);
}());
}(),function(){
var e=document.getElementById("js_hotspot_area"),t=0===window.hotspotInfoList.length,o=function i(o){
if(!t){
var n=x.getInnerHeight()+(window.pageYOffset||document.documentElement.scrollTop||document.body.scrollTop);
e.offsetTop<n?(t=!0,h.off(window,"scroll",i),(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=59977_15_1",
b.hotspotReport({
hotspotjson:JSON.stringify({
hotspotinfolist:window.hotspotInfoList
})
})):"function"==typeof o&&o();
}
};
o(function(){
h.on(window,"scroll",o);
});
}();
var et=/^http(s)?:\/\/mp\.weixin\.qq\.com\//g;
try{
if(top!=window&&(!top||top&&location.href&&et.test(location.href))&&!window.isSg)throw new Error("in iframe");
}catch(J){
var tt="",ot=new Image;
ot.src=("http://mp.weixin.qq.com/mp/jsreport?key=4&content=biz:"+biz+",mid:"+mid+",uin:"+uin+"[key4]"+tt+"&r="+Math.random()).substr(0,1024);
}
if(window.isInWeixinApp()&&/#rd$/.test(location.href)&&!window.isWeixinCached&&!window.__second_open__){
var it=-1!=location.href.indexOf("?")?"&":"?";
location.replace(location.href.replace(/#rd$/,it+"rd2werd=1#wechat_redirect"));
}
var nt=e("biz_common/utils/url/parse.js");
e("appmsg/cdn_img_lib.js"),window.page_endtime=+new Date;
{
var rt=!_.isWp&&-1==navigator.userAgent.indexOf("MicroMessenger");
-1!=navigator.userAgent.indexOf("WindowsWechat");
}
e("appmsg/share.js");
var at=v(1e3*parseInt(window.modify_time)),dt=at.format("YYYY-MM-DD"),st=document.getElementById("js_modify_time");
if(st&&(st.innerHTML=dt),window.isSg||"mp.weixin.qq.com"==location.host){
var pt=e("biz_common/log/jserr.js");
pt({
key:0,
reporturl:"http://mp.weixin.qq.com/mp/jsreport?1=1",
replaceStr:/http(s)?:(.*?)js\//g
});
}
window.logs.webplog={
lossy:0,
lossless:0,
alpha:0,
animation:0,
total:0
};
var ct=-1!=navigator.userAgent.indexOf("TBS/"),mt=function(e,t){
H(e,function(e,o){
if(window.logs.webplog[e]=o?1:0,window.logs.webplog.total++,4==window.logs.webplog.total){
var i=window.logs.webplog,n=Math.random();
ct&&1>=n&&(i.lossy=i.lossless=i.alpha=1,window.logs.webplog=i);
var r=i.lossy&i.lossless&i.alpha;
t(!!r);
}
});
},lt=function(e){
for(var t=document.getElementsByTagName("img"),o=!1,i=!1,n=0,r=t.length;r>n;n++){
var a=t[n].getAttribute("data-src");
a&&a.canHevc()&&(o=!0),a&&a.isGif()&&(i=!0);
}
var d=_.gtVersion("6.5.13",!0)&&i,s=_.gtVersion("6.8.0",!0)&&o,p=!1;
try{
{
top.window.document;
}
}catch(c){
p=!0;
}
(R||navigator.userAgent.indexOf("Br_trunk")>-1)&&_.isIOS&&(d||s)&&!p?(console.info("[HEVC代理] 当前版本可以启用HEVC代理"),
y.invoke("imageProxyInit",{},function(t){
t.err_msg.indexOf(":ok")>-1?(C=t.serverUrl,window.__addIdKeyReport("28307",117)):t.err_msg.indexOf(":fail")>-1&&window.__addIdKeyReport("28307",118),
e();
})):e();
},wt=function(e){
mt("lossy",e),mt("lossless",e),mt("alpha",e),mt("animation",e);
};
window.webp=!1,lt(function(){
wt(function(t){
function o(e){
e.width<40||e.height<40||-1==e.className.indexOf("img_loading")&&(e.className+=" img_loading");
}
function i(e){
if(!(e.width<40||e.height<40)){
var t=e.src;
if(e.className=e.className.replace("img_loading",""),-1==e.className.indexOf("img_loadederror")){
e.className+=" img_loadederror",e.src="data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==",
window.__addIdKeyReport("28307",51);
var i=function(){
window.__addIdKeyReport("28307",66),n(e),o(e);
var i=e.__retryload;
return i=0,t=t.https2http(),e.__retryload=i,e.src=nt.addParam(t,"retryload",i,!0),
!1;
};
h.on(e,"click",i);
}
}
}
function n(e){
e.className=e.className.replace("img_loading",""),e.className=e.className.replace("img_loadederror","");
}
window.webp=t,t&&window.localStorage&&window.localStorage.setItem&&window.localStorage.setItem("webp","1"),
window.logs.img={
download:{},
read:{},
load:{}
};
var r=document.getElementById("js_cover");
if(r){
var a=r.getAttribute("data-src");
a&&(a.isCDN()&&(a=a.imgChange640(),t&&(a=nt.addParam(a,"tp","webp",!0)),a=nt.addParam(a,"wxfrom","5",!0),
is_https_res||T?a=a.http2https():("http:"==location.protocol||-1!=navigator.userAgent.indexOf("MicroMessenger"))&&(a=a.https2http())),
setTimeout(function(){
r.onload=function(){
g(r,"height","auto","important"),g(r,"visibility","visible","important");
},r.setAttribute("src",a);
},0),window.logs.img.read[a]=!0,window.logs.img.load[a]=!0,r.removeAttribute("data-src"));
}
var d=e("biz_wap/ui/lazyload_img.js"),s=2;
window.logs.outer_pic=0;
for(var p=document.getElementsByTagName("img"),l=0,w=p.length;w>l;l++){
{
var u=p[l].getAttribute("data-src");
p[l].getAttribute("src");
}
u&&u.isGif()&&p[l].className.indexOf("__bg_gif")<0&&(p[l].className+=" __bg_gif");
}
for(var f=document.getElementsByClassName("__bg_gif"),l=0,w=f.length;w>l;++l)f[l].setAttribute("data-order",l);
var y=function(e){
try{
var t=e,o=t.getAttribute("data-src");
if(!/^https?\:\/\/mmbiz\.qpic\.cn/.test(o))return;
var i=t.parentNode,n=!1;
c.hasClass(i,"js_jump_icon")&&(n=!0);
for(var r=!1;i.tagName&&"body"!=i.tagName.toLowerCase();){
if("a"==i.tagName.toLowerCase()){
var a=i.getAttribute("href")||"";
null!=a.match(/^http/)&&(r=!0);
break;
}
i=i.parentNode;
}
if(n&&!r){
var d=t.parentNode,s=d.parentNode;
if(s){
for(var p=document.createDocumentFragment();d.firstChild;)p.appendChild(d.firstChild);
s.insertBefore(p,d),s.removeChild(d);
}
}else if(!n&&r){
var m=document.createElement("span"),l=getComputedStyle(t);
"static"!=l.positon&&(m.style.position=l.positon),m.style.left=l.left,m.style.top=l.top,
m.style.right=l.right,m.style.bottom=l.bottom,m.style.margin=l.margin,c.addClass(m,"js_jump_icon"),
c.addClass(m,"h5_image_link"),t.style.position="static",t.style.margin="0px",t.parentNode.insertBefore(m,t),
m.appendChild(t),window.__addIdKeyReport("111535",0);
}
}catch(w){}
},v=function S(e){
try{
var t=e.childNodes,o=getComputedStyle(e);
(o.backgroundImage.match(/https\:\/\/mmbiz\.qpic\.cn/)||o.backgroundImage.match(/http\:\/\/mmbiz\.qpic\.cn/))&&window.__addIdKeyReport("111535",2);
for(var i=0;i<t.length;i++)"a"!=t[i].tagName.toLowerCase()&&S(t[i]);
}catch(n){}
};
try{
for(var b=document.getElementsByTagName("a"),A=0;A<b.length;A++){
var I=b.item(A),x=I.getAttribute("href")||"";
null!=x.match(/^http/)&&v(I);
}
}catch(k){}
var E=!1;
new d({
attrKey:"data-src",
imgOccupied:!0,
crossOrigin:!0,
lazyloadHeightWhenWifi:function(){
var e,t=1,o=1;
e=window.svr_time?new Date(1e3*window.svr_time):new Date;
var i=e.getHours();
return i>=20&&23>i&&(t=.5,o=0),{
bottom:t,
top:o
};
},
inImgRead:function(e){
e&&(window.logs.img.read[e]=!0);
},
changeSrc:function(e,t){
if(!t)return"";
var o=t;
if(t.isCDN()){
o=o.imgChange640();
var i,n=window.navigator.userAgent,r=/TBS\/([\d\.]+)/i,a=n.match(r);
a&&a[1]&&(i=parseInt(a[1]));
var d,s=/XWEB\/([\d\.]+)/i,p=n.match(s);
p&&p[1]&&(d=parseInt(p[1]));
var c=1e3,l=window.user_uin||0,w=0!==l&&Math.floor(l/100)%1e3<c,g=(i>=43305&&44206!=i||d>=16)&&o.isGif(),u=0!==l&&Math.floor(l/100)%1e3<=500,f=d>=564&&o.canHevc()&&_.gtVersion("6.8.0",!0)&&u;
w&&(g||f)?(o=nt.addParam(o,"tp","wxpic",!0),window.__addIdKeyReport("28307",91)):window.webp&&(o=nt.addParam(o,"tp","webp",!0),
window.__addIdKeyReport("28307",84)),o=nt.addParam(o,"wxfrom","5",!0),is_https_res||T?(o=o.http2https(),
window.__addIdKeyReport("28307",77)):("http:"==location.protocol||-1!=navigator.userAgent.indexOf("MicroMessenger"))&&(o=o.https2http(),
window.__addIdKeyReport("28307",70));
}else try{
var r=new RegExp("^http(s)?://((mmbiz.qpic.cn/.*)|(m.qpic.cn/.*)|(mmsns.qpic.cn/.*)|(shp.qpic.cn/.*)|(wx.qlogo.cn/.*)|(mmbiz.qlogo.cn/.*)|((a|b)[0-9]*.photo.store.qq.com/.*)|(mp.weixin.qq.com/.*)|(res.wx.qq.com/.*))");
r.test(t)||(window.__addIdKeyReport("28307",9),window.logs.outer_pic++);
}catch(h){}
var y=/^http\:\/\/(a|b)(\d)+\.photo\.store\.qq\.com/g;
o=o.replace(y,"http://m.qpic.cn"),/^http(s)?:\/\/m\.qpic\.cn([\/?].*)*$/i.test(o)&&!window.webp&&(o=nt.addParam(o,"t","",!0)),
o=nt.addParam(o,"wx_lazy","1",!0);
var v=_.gtVersion("6.5.13",!0)&&!_.eqVersion("7.0.9")&&o.isGif(),b=_.gtVersion("6.8.0",!0)&&o.canHevc()&&!(_.eqVersion("7.0.9")&&o.isGif());
return C&&(v||b)&&(window.__addIdKeyReport("28307",106),o=nt.addParam(o,"tp","wxpic",!0),
o=C+"hevc?url="+encodeURIComponent(o)+"&type="+o.getOriginImgType()),"anonymous"==e.crossOrigin&&(o=nt.addParam(o,"wx_co","1",!0)),
window.logs.img.load[o]=!0,m("[Appmsg] image_load_event_change_src. originsrc:"+t+"  ^^^ newsrc : "+o),
e.start_load_time=+new Date,o;
},
onerror:function(e,t){
var o=t?t.__retryload||0:0;
if(2==o&&i(t),e&&!(o>s)){
if(!e.isCDN()){
if(!C)return;
if(-1==e.indexOf(C))return;
}
var n=0==e.indexOf("https://")?7:0;
if(window.__addIdKeyReport("28307",72+n),1>=o&&window.__addIdKeyReport("28307",75+1*o+n),
e.isWxpic()?(window.__addIdKeyReport("28307",93),1>=o&&window.__addIdKeyReport("28307",96+1*o)):e.isWebp()&&(window.__addIdKeyReport("28307",86),
1>=o&&window.__addIdKeyReport("28307",89+1*o)),C&&e.indexOf(C)>-1&&window.__addIdKeyReport("28307",108),
s>o){
if(o++,t.__retryload=o,1==o&&e.indexOf("http://")>-1?(e=e.http2https(),window.__addIdKeyReport("28307",60),
window.__addIdKeyReport("28307",77)):1==o&&e.indexOf("https://")>-1?(window.__addIdKeyReport("28307",61),
window.__addIdKeyReport("28307",77)):2==o&&e.indexOf("mmbiz.qpic.cn")>-1&&(e=e.replace("mmbiz.qpic.cn","mmbiz.qlogo.cn"),
e.indexOf(!1)&&(e=e.http2https())),C&&e.indexOf(C)>-1){
var r=e.split("hevc?url=")[1];
r=r.split("&type")[0],r=decodeURIComponent(r),r=r.replace("tp=wxpic",""),e=r.https2http();
}
t.start_load_time=+new Date,t.src=nt.addParam(e,"retryload",o,!0);
}
window.__has_imgfailed||(window.__has_imgfailed=!0,window.__addIdKeyReport("28307",65)),
m("[Appmsg] image_load_event_on_error. src:"+e),t.setAttribute("data-fail",1);
try{
if("[object Array]"==Object.prototype.toString.call(t.lazyLoadOnerror))for(var a=0,d=t.lazyLoadOnerror.length;d>a;a++)"function"==typeof t.lazyLoadOnerror[a]&&t.lazyLoadOnerror[a].call(t);
}catch(p){}
var c=10;
/tp\=webp/.test(e)&&(c=11);
var l=new Image;
l.src="http://mp.weixin.qq.com/mp/jsreport?key="+c+"&content="+(encodeURIComponent(e)+"["+uin+"]")+"&r="+Math.random();
}
},
onload:function(e,t){
if(!window.__second_open__&&!E){
var o=window.performance||window.msPerformance||window.webkitPerformance;
if(!o||!o.timing)return;
var i=window.location.protocol;
j.saveSpeeds({
uin:uin,
pid:"https:"==i?462:417,
speeds:{
sid:35,
time:Date.now()-window.performance.timing.navigationStart
}
}),j.send(),E=!0;
}
n(t),t.gray&&!t.loadGif&&((t.width||t.naturalWidth)<120||(t.height||t.naturalHeight)<120?t.autoTap&&t.autoTap():t.span&&t.span.children&&t.span.children.item(0)&&(t.span.children.item(0).style.display=""));
var r=t?t.__retryload||0:0;
if(!(r>s)){
m("[Appmsg] image_load_event_onload_image. src:"+e+"  ^^^  retryloadtimes: "+r),
t.setAttribute("data-fail",0),y(t);
try{
if("[object Array]"==Object.prototype.toString.call(t.lazyLoadOnload))for(var a=0,d=t.lazyLoadOnload.length;d>a;a++)"function"==typeof t.lazyLoadOnload[a]&&t.lazyLoadOnload[a].call(t);
}catch(p){}
var c=0==e.indexOf("https://")?7:0;
window.__addIdKeyReport("28307",71+c),1>=r&&window.__addIdKeyReport("28307",73+1*r+c),
e.isWxpic()?(window.__addIdKeyReport("28307",92),1>=r&&window.__addIdKeyReport("28307",94+1*r)):e.isWebp()&&(window.__addIdKeyReport("28307",85),
1>=r&&window.__addIdKeyReport("28307",87+1*r)),C&&e.indexOf(C)>-1&&window.__addIdKeyReport("28307",107),
window.__has_imgsucceed||(window.__has_imgsucceed=!0,window.__addIdKeyReport("28307",64)),
1==r&&e.indexOf("http://")>-1&&window.__addIdKeyReport("28307",50),1==r&&e.indexOf("https://")>-1&&window.__addIdKeyReport("28307",52);
var l=Math.random(),w=+new Date-t.start_load_time;
w&&0==e.indexOf("https://")&&.5>l?(window.__addIdKeyReport("27822",121,w),window.__addIdKeyReport("27822",122)):w&&5e-4>l&&(window.__addIdKeyReport("27822",124,w),
window.__addIdKeyReport("27822",125)),"none"!=getComputedStyle(t).filter&&(t.style.transform="translateZ(0)",
t.style.webkitTransform="translateZ(0)");
}
},
detect:function(e){
if(e&&e.time&&e.loadList){
var t=e.time,o=e.loadList;
window.logs.img.download[t]=o;
}
},
container:document.getElementById("page-content")
});
});
}),e("appmsg/async.js"),!window.isSg;
var gt=e("appmsg/copyright_report.js");
!function(){
var e=document.getElementById("profileBt"),t=document.getElementById("copyright_info"),o=[];
if(_.isInMiniProgram&&t&&c.addClass(t,"disabled"),e){
var i="57";
"28"==window.source&&(i="96"),"29"==window.source&&(i="39"),"15"==window.source&&(i="121"),
o.push({
dom:e,
username:user_name_new||user_name,
profileReportInfo:window.profileReportInfo||"",
scene:i
});
}
t&&source_encode_biz&&o.push({
dom:t,
source_encode_biz:source_encode_biz,
scene:"161"
});
var n=document.getElementById("js_share_headimg");
n&&o.push({
dom:n,
username:source_username,
scene:"172"
});
var r=document.getElementById("js_share_author");
r&&o.push({
dom:r,
username:source_username,
scene:"172"
});
for(var a=0,d=o.length;d>a;a++)!function(e){
h.on(e.dom,"click",function(){
if("copyright_info"==e.dom.id&&source_encode_biz){
if(_.isInMiniProgram)return!1;
gt.card_click_report({
scene:"0"
});
var t="https://mp.weixin.qq.com/mp/profile_ext?action=home&__biz="+e.source_encode_biz+"&scene="+e.scene+"#wechat_redirect";
-1!=navigator.userAgent.indexOf("WindowsWechat")?location.href=t:y.invoke("profile",{
username:source_username,
scene:e.scene+""
});
}else{
if(m("[Appmsg] profile_click_before_loadprofile: username:"+e.username+", scene:"+e.scene),
b.profileReport({
hotspotjson:JSON.stringify({
hotspotinfolist:window.hotspotInfoList
})
}),profileReportInfo){
var o=String(profileReportInfo).split("_");
3==o.length&&l({
url:"/mp/ad_biz_info?action=report&__biz="+window.biz+"&report_type=2&aid="+o[1]+"&tid="+o[2],
type:"GET",
dataType:"json",
async:!0,
success:function(){}
});
}
_.isInMiniProgram||(1==isprofileblock?y.invoke("openUrlWithExtraWebview",{
url:"https://mp.weixin.qq.com/mp/profileblock?__biz="+window.biz+"#wechat_redirect",
openType:1
},function(e){
-1==e.err_msg.indexOf("ok")&&(location.href="https://mp.weixin.qq.com/mp/profileblock?__biz="+window.biz+"#wechat_redirect");
}):y.invoke("profile",{
username:e.username,
profileReportInfo:e.profileReportInfo||"",
scene:e.scene+""
},function(t){
window.__addIdKeyReport("28307","1"),m("[Appmsg] profile_click_after_loadprofile: username:"+e.username+", scene:"+e.scene+", profileReportInfo:"+e.profileReportInfo+", res.err_msg:"+t.err_msg);
}));
}
return!1;
}),_.isWp&&e.dom.setAttribute("href","weixin://profile/"+e.username);
}(o[a]);
}(),function(){
function e(){
if("hidden"in document)return"hidden";
for(var e=["webkit","moz","ms","o"],t=0;t<e.length;t++)return e[t]+"Hidden"in document,
e[t]+"Hidden";
return null;
}
function t(){
var t=e();
return t?document[t]:!1;
}
function o(){
if(t())for(var e=0;e<window.parent.originalVideoAdFrames.length;e++)window.parent.originalVideoAdFrames[e].contentWindow.postMessage({
action:"pauseAd",
value:""
},"*");else{
var o=document.documentElement.scrollTop||window.pageYOffset||document.body.scrollTop;
o>=40&&y.invoke("currentMpInfo",{
userName:window.user_name,
brandName:D,
title:window.msg_title||"",
brandIcon:hd_head_img.replace(/\/0$/,"/132"),
itemShowType:window.item_show_type,
isPaySubscribe:window.isPaySubscribe,
topBarStyle:M?1:0,
topBarShowed:!0
},function(){}),window.originalVideoAdCurrentFrame&&window.originalVideoAdCurrentFrame.contentWindow.postMessage({
action:"playAd"
},"*");
}
}
document.webkitVisibilityState?document.addEventListener("webkitvisibilitychange",o,!1):document.msVisibilityState?document.addEventListener("msvisibilitychange",o,!1):document.visibilityState&&document.addEventListener("visibilitychange",o,!1);
}();
try{
var ut=document.getElementById("js_author_name");
if(ut){
var _t="";
h.on(ut,"click",function(){
return c.hasClass(ut,"rich_media_meta_link")?window.is_temp_url?(window.weui.alert("预览状态下不能操作"),
!1):ut.getAttribute("data-rewardsn")?1!=ut.getAttribute("data-canreward")?!1:(_t="https://mp.weixin.qq.com/mp/author?action=show&author_id="+author_id+"&rewardsn="+ut.getAttribute("data-rewardsn")+"&timestamp="+ut.getAttribute("data-timestamp")+"&__biz="+window.biz+"&appmsgid="+window.appmsgid+"&idx="+window.idx+"&scene=142&rscene=129#wechat_redirect",
_.isInMiniProgram?!1:(-1!=navigator.userAgent.indexOf("MicroMessenger")&&(_.isIOS||_.isAndroid||_.isWp)?(window.__addIdKeyReport("110809","1"),
y.invoke("openUrlWithExtraWebview",{
url:_t,
openType:1
},function(e){
-1==e.err_msg.indexOf("ok")&&(location.href=_t);
})):location.href=_t,!1)):!1:!1;
});
}
}catch(J){}
var ft=e("appmsg/outer_link.js");
if(new ft({
container:document.getElementById("js_content"),
changeHref:function(e,t){
if(!e||0!=e.indexOf("http://mp.weixin.qq.com/")&&0!=e.indexOf("https://mp.weixin.qq.com/")){
if(18==ban_scene)return"/mp/ban?action=check&__biz="+biz+"&mid="+mid+"&idx="+idx+"&scene="+ban_scene+"#wechat_redirect";
if(0!=e.indexOf("http://mp.weixinbridge.com/mp/wapredirect"))return"http://mp.weixinbridge.com/mp/wapredirect?url="+encodeURIComponent(e)+"&action=appmsg_redirect&uin="+uin+"&biz="+biz+"&mid="+mid+"&idx="+idx+"&type="+t+"&scene=0";
}else{
e=e.replace(/#rd\s*$/,""),e=e.replace(/#wechat_redirect\s*$/,""),e=e.replace(/[\?&]scene=21/,"");
var o="&";
-1==e.indexOf("?")&&(o="?"),e+=o+"scene=21#wechat_redirect";
}
return e;
}
}),!rt){
var ht=e("appmsg/review_image.js"),yt=document.getElementById("js_cover"),vt=[];
yt&&vt.push(yt),new ht({
container:document.getElementById("js_content"),
is_https_res:is_https_res,
imgs:vt
});
}
e("appmsg/product.js");
var bt=e("appmsg/page_pos.js");
bt.init({
hasSpAd:!0,
disableScroll:window.isPaySubscribe&&!window.isPaid&&window.jump2pay
}),function(){
try{
var e=document.getElementById("js_content");
if(!e||!e.querySelectorAll)return;
var t=function(e){
var t=e.getAttribute("class");
if(t){
for(var o=t.split(/\s+/),i=[],n=0,r=o.length;r>n;++n){
var a=o[n];
if(a&&-1!=window.whiteList.indexOf(a))i.push(a);else for(var d=0,s=window.whiteListReg.length;s>d;d++)if(window.whiteListReg[d].test(a)){
i.push(a);
break;
}
}
e.setAttribute("class",i.join(" "));
}
};
e.querySelectorAll("*").forEach(function(e){
if(e&&e.tagName){
var o=e.tagName.toLowerCase();
"iframe"!==o?t(e):"video_ad_iframe"===e.getAttribute("class")&&e.setAttribute("class","");
}
});
}catch(o){
console.error(o);
}
}(),function(){
window.originalVideoAdFrames=[],window.originalVideoAdCurrentFrame=null,window.originalVideoAdFramesUnsetList=[],
window.addEventListener("message",function(e){
var t="",o=document.getElementsByTagName("iframe");
if(e.data&&"originalVideoAdNeedData"==e.data.action&&e.data.vid)if(window.originalVideoAdFramesAdData){
window.originalVideoAdFramesAdData&&window.originalVideoAdFramesAdData[e.data.vid]&&(t=window.originalVideoAdFramesAdData[e.data.vid]);
for(var i=0;i<o.length;i++)o[i].dataset&&o[i].dataset.mpvid==e.data.vid&&o[i].contentWindow.postMessage({
action:"receiveOriginalVideoData",
vid:e.data.vid,
adData:t
},"*");
}else console.log(e.data.vid," has no ad data yet"),window.originalVideoAdFramesUnsetList.push(e.data.vid);
});
}(),window.fromWeixinCached||e("appmsg/iframe.js"),I.getAdData(window.reportVid),
e("appmsg/qqmusic.js"),e("appmsg/voice.js"),e("redpackage/redpacketcover.js"),window.__appmsgCgiData&&1==window.__appmsgCgiData.show_msg_voice&&e("appmsg/autoread.js"),
"1"==window.show_msg_voice&&(console.log("load voicemsg"),e("appmsg/voicemsg.js")),
!window.__appmsgCgiData||1!=window.__appmsgCgiData.wxa_product&&1!=window.__appmsgCgiData.wxa_cps||e("appmsg/weproduct.js"),
e("appmsg/weapp.js"),e("question_answer/appmsg.js"),e("appmsg/wxtopic.js"),e("appmsg/cdn_speed_report.js");
var At=e("appmsg/appmsg_copy_report.js");
new At({
biz:window.biz,
isPaySubscribe:window.isPaySubscribe,
container:document.getElementById("js_content"),
logid:18504,
baseData:["",window.biz,window.mid,window.idx,window.location.href,window.msg_title]
}),setTimeout(function(){
window.article_improve_combo_css;
},0),setTimeout(function(){
h.tap(document.getElementById("copyright_logo"),function(){
var e="http://kf.qq.com/touch/sappfaq/150211YfyMVj150326iquI3e.html";
window.__second_open__?y.invoke("openUrlWithExtraWebview",{
url:e,
openType:1
},function(t){
-1==t.err_msg.indexOf("ok")&&(location.href=e);
}):location.href=e;
}),u(),f(),h.tap(document.getElementById("js_hotspot_area"),function(e){
if(c.hasClass(e.target,"js_hotspot")){
var t=e.target.dataset.id;
if(!t)return;
t="https://search.weixin.qq.com/cgi-bin/searchweb/clientjump?scene=306&tag=mp_topic&topic_id="+t+"#wechat_redirect",
-1!=navigator.userAgent.indexOf("MicroMessenger")&&(_.isIOS||_.isAndroid||_.isWp)?y.invoke("openUrlWithExtraWebview",{
url:t,
openType:1
},function(e){
-1==e.err_msg.indexOf("ok")&&(location.href=t);
}):location.href=t;
}
}),e("appmsg/report_and_source.js"),function(){
if(rt){
document.title=window.msg_title.htmlDecode(),c.addClass(Z,"not_in_mm");
var e=document.getElementById("js_pc_qr_code_img");
if(e){
var t=10000004,o=document.referrer;
if(0==o.indexOf("http://weixin.sogou.com")?t=10000001:0==o.indexOf("https://wx.qq.com")&&(t=10000003),
window.isSg)e.setAttribute("src",sg_qr_code.htmlDecode());else{
e.setAttribute("src","/mp/qrcode?scene="+t+"&size=102&__biz="+biz+"&mid="+mid+"&idx="+idx+"&sn="+sn+"&send_time="+send_time);
var i=new Image;
i.src="/mp/report?action=pcclick&__biz="+biz+"&uin="+uin+"&scene="+t+"&r="+Math.random();
}
document.getElementById("js_pc_qr_code").style.display="block";
}
var n=document.getElementById("js_profile_qrcode"),r=document.getElementById("js_profile_arrow_wrp"),a=document.getElementById("profileBt");
if(n&&a&&r){
var d=function(){
var e=10000005,t=document.referrer;
0==t.indexOf("http://weixin.sogou.com")?e=10000006:0==t.indexOf("https://wx.qq.com")&&(e=10000007);
var o=document.getElementById("js_profile_qrcode_img");
if(o)if(window.isSg)o.setAttribute("src",sg_qr_code.htmlDecode());else{
o.setAttribute("src","/mp/qrcode?scene="+e+"&size=102&__biz="+biz+"&mid="+mid+"&idx="+idx+"&sn="+sn+"&send_time="+send_time);
var i=new Image;
i.src="/mp/report?action=pcclick&__biz="+biz+"&uin="+uin+"&scene="+e+"&r="+Math.random();
}
return n.style.display="block",r.style.left=a.offsetWidth/2-8+"px",!1;
};
h.on(a,"click",d),h.on(n,"click",d),h.on(document,"click",function(e){
var t=e.target||e.srcElement;
t!=a&&t!=n&&(n.style.display="none");
});
}
}else{
var s=document.getElementById("js_report_article3");
!!s&&(s.style.display="");
}
}(),function(){
var e=location.href.indexOf("scrolltodown")>-1?!0:!1,t=document.getElementById("img-content");
if(e&&t&&t.getBoundingClientRect){
var o=t.getBoundingClientRect().height;
window.scrollTo(0,o);
}
}(),e("appmsg/report.js");
for(var t=document.getElementsByTagName("map"),o=0,i=t.length;i>o;++o)t[o].parentNode.removeChild(t[o]);
if(gt.card_pv_report(),Math.random()<.01)try{
var n="https://js.aq.qq.com/js/aq_common.js",r=document.createElement("script");
r.src=n;
var a=document.getElementsByTagName("head")[0];
a.appendChild(r);
}catch(d){}
var s=document.getElementById("js_close_temp");
h.on(s,"click",function(){
s.parentNode.parentNode.removeChild(s.parentNode),c.removeClass(document.getElementById("js_article"),"preview_appmsg");
});
},1e3),function(){
if(p.os.ios&&"onorientationchange"in window){
var e=[],t="onorientationchange"in window?"orientationchange":"resize",o=function(){
return 90===Math.abs(window.orientation)?1:2;
};
e.push({
ori:o(),
scroll:window.pageYOffset||document.documentElement.scrollTop,
istouchmove:!1
});
var i=(new Date).getHours();
h.on(window,t,function(){
var t=e.length-2,n=o();
if(P=+new Date,t>=0){
{
var r=e[t];
r.ori;
}
e[e.length-1].istouchmove||(i>=11&&17>=i&&window.__report(63),setTimeout(function(){
window.scrollTo(0,r.scroll);
},100));
}
e.push({
ori:n,
scroll:window.pageYOffset||document.documentElement.scrollTop,
istouchmove:!1
});
});
var n=document.getElementById("js_hotspot_area"),r=0===n.children.length;
h.on(window,"scroll",function(){
var t=e.length-1,i=window.pageYOffset||document.documentElement.scrollTop||document.body.scrollTop,a=+new Date;
if(-1!=P){
if(console.log("[横屏滚动检测]",a-P),500>a-P)return void(P=-1);
}else P=-1;
if(e[t].ori==o()&&(e[t].scroll=i,e[t].istouchmove=!0,!r)){
var d=x.getInnerHeight()+i;
n.offsetTop<d&&(r=!0,(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=59977_15_1");
}
});
}
}(),m("[Appmsg] href:"+location.href+"^^^ ua:"+window.navigator.userAgent),window.addEventListener?window.addEventListener("load",U,!1):window.attachEvent&&window.attachEvent("onload",U),
e(window.moon&&moon.clearSample?"appmsg/fereport_without_localstorage.js":"appmsg/fereport.js"),
function(){
window.addEventListener&&document.getElementsByTagName("body")[0].addEventListener("copy",function(){
(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_18_1",
_.isIOS&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_19_1"),
_.isAndroid&&((new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_20_1");
},!1);
}(),function(){
window.__observer&&window.__observer_data&&e("biz_wap/safe/mutation_observer_report.js");
}(),"undefined"!=typeof isSg&&e("sougou/index.js"),setTimeout(function(){
for(var e=function(){
(new Image).src=location.protocol+"//mp.weixin.qq.com/mp/jsmonitor?idkey=28307_49_1&lc=1&log0=[28307_49_appmsg_fe_filter]"+encodeURIComponent(location.href);
},t=(window.appmsg_fe_filter||"").split(","),o=function(t,o){
try{
if(!t)return;
if(t.querySelectorAll){
var i=t.querySelectorAll("*["+o+"]");
if(i&&i.length>0){
e();
for(var n=0;n<i.length;++n)i[n]&&i[n].removeAttribute&&i[n].removeAttribute(o);
}
return;
}
var r=t.childNodes;
if(t.hasAttribute&&t.hasAttribute(o)&&e(),t.removeAttribute&&t.removeAttribute(o),
r&&r.length)for(var n=0;n<r.length;++n)filterContenteditable(r[n]);
}catch(a){}
},i=document.getElementById("js_content"),n=0;n<t.length;++n)t[n]&&o(i,t[n]);
},0),setTimeout(function(){
var e=999,t=636,o="http://mmbiz.qpic.cn/mmbiz_png/7lG1x2vpicdic0p5bBthpD9lsJcINicsSzd6uKQQJyoj5oTl8lFIs9K0fIibgxCzms0enDLTRxTHLpDPCLpSvIExiag/0",i=(new Date).getHours();
if(!(11>i||i>16||Math.random()<.99)){
var n=new Image;
n.onload=function(){
var o=n.naturalWidth||n.width,i=n.naturalHeight||n.height;
(o!=e||i!=t)&&window.__addIdKeyReport("28307","wifi"===window.networkType?120:123),
window.__addIdKeyReport("28307","wifi"===window.networkType?121:124);
},n.src=o;
var r=new Image;
r.onload=function(){
var o=r.naturalWidth||r.width,i=r.naturalHeight||r.height;
(o!=e||i!=t)&&window.__addIdKeyReport("28307",126),window.__addIdKeyReport("28307",127);
},r.src="https://mmbiz.qpic.cn/mmbiz_png/7lG1x2vpicdic0p5bBthpD9lsJcINicsSzd6uKQQJyoj5oTl8lFIs9K0fIibgxCzms0enDLTRxTHLpDPCLpSvIExiag/0";
}
},3e3);
var It=Math.random();
if(2e-4>It)try{
for(var jt=document.getElementsByTagName("img"),xt=window.screen.height,kt=window.screen.width,Et=0,St=window.devicePixelRatio,Et="",Q=0,Pt=jt.length;Pt>Q;Q++){
var zt=jt[Q].getAttribute("data-src");
if(zt){
var Bt=jt[Q].getBoundingClientRect();
Et+=kt+"|"+xt+"|"+Bt.left.toFixed(2)+"|"+(kt-Bt.right).toFixed(2)+"|"+Bt.width.toFixed(2)+"|"+St.toFixed(2)+"|"+zt+";";
}
}
l({
url:"/mp/wapreport?action=img_display_report",
data:{
key:Et
},
type:"POST",
dataType:"json",
async:!0
});
}catch(J){}
setTimeout(function(){
z&&z.postPageHeightMessage&&z.postPageHeightMessage("updatePageHeight");
},2e3),_.isIOS&&location.href.match(/fontScale=\d+/)&&p.os.ipad&&p.os.getNumVersion()>=13&&setTimeout(function(){
if(!window.ipados13_has_init_setfont){
var e=location.href.match(/fontScale=(\d+)/);
i(document.getElementsByTagName("html").item(0),parseFloat(e[1])/100);
}
},500);
}
e("biz_wap/ui/weui.js");
var i=e("appmsg/set_font_size.js"),n=e("biz_common/tmpl.js"),r=e("cps/tpl/banner_tpl.html.js"),a=e("cps/tpl/card_tpl.html.js"),d=e("cps/tpl/list_tpl.html.js");
e("biz_common/utils/string/html.js");
var s=e("appmsg/weapp_common.js"),p=e("biz_wap/utils/device.js"),c=e("biz_common/dom/class.js"),m=e("appmsg/log.js"),l=e("biz_wap/utils/ajax.js"),w=e("biz_common/dom/attr.js"),g=w.setProperty,u=e("appmsg/max_age.js"),_=e("biz_wap/utils/mmversion.js"),f=e("appmsg/test.js"),h=e("biz_common/dom/event.js"),y=e("biz_wap/jsapi/core.js"),v=e("biz_common/moment.js"),b=e("appmsg/appmsg_report.js"),A=e("biz_common/utils/url/parse.js"),I=e("a/mpAdAsync.js"),j=e("biz_wap/utils/wapsdk.js"),x=e("common/utils.js"),k=(e("complain/localstorage.js"),
e("appmsg/popup_report.js")),E=e("appmsg/pay_report_utils.js"),S=e("appmsg/loading.js"),P=-1,z=e("appmsg/finance_communicate.js"),B=e("common/comm_report.js");
window.new_appmsg&&(e("page/appmsg_new/combo.css"),e("page/appmsg_new/not_in_mm.css")),
e("appmsg/finance_communicate.js");
var q=window.user_uin||0,O=Math.floor(q/100)%1e3,T=0!==q&&1001>O,R=!0,C="",N=5,M=_.isIOS&&_.gtVersion("7.0.10",!0)||_.isAndroid&&_.gtVersion("7.0.12",!0),D=M&&""===window.nickname&&""===window.nickname_new?"未命名公众号":window.title;
if(window.logs.pagetime.jsapi_ready_time=+new Date,window.logs.idkeys={},console.info("[图文信息] 三元组:",window.biz,window.mid,window.idx),
console.info("[用户信息] 设备信息: 是否安卓",p.os.android,"是否IOS",p.os.ios,"是否秒开场景",window.__second_open__,"系统版本",p.os.version,"用户uin",window.user_uin),
m("[Appmsg] start run index.js init"),function(){
var e=(new Date).getHours(),t=function(e,t){
t=t||"",window.isSg?(t=["uin:sougou","resp:"+t].join("|"),(new Image).src="/mp/jsreport?key="+e+"&content="+t+"&r="+Math.random()+"&from=sougou"):(t=["uin:"+window.user_uin,"resp:"+t].join("|"),
(new Image).src="/mp/jsreport?key="+e+"&content="+t+"&r="+Math.random());
},o=function(e,t,o){
var i=e+"_"+t;
o=o||1,window.logs.idkeys[i]||(window.logs.idkeys[i]={
val:0
}),window.logs.idkeys[i].val+=o;
},i=e>=11&&17>=e&&Math.random()<1,n=function(e,o){
i&&t(e,o);
};
window.__report=t,window.__commonVideoReport=n,window.__addIdKeyReport=o;
}(),o(),!window.__second_open__){
var L=window.performance||window.msPerformance||window.webkitPerformance;
if(!L||!L.timing)return;
var K=window.location.protocol;
j.saveSpeeds({
uin:uin,
pid:"https:"==K?462:417,
speeds:{
sid:34,
time:Date.now()-window.performance.timing.navigationStart
}
}),j.send();
}
!function(){
(_.isIOS||_.isAndroid)&&!function(){
j.jsmonitor({
id:125350,
key:window.__second_open__?_.isIOS?0:2:_.isIOS?1:3
});
var e=!1;
h.on(window,"beforeunload",function(){
e||(e=!0,j.jsmonitor({
id:125350,
key:window.__second_open__?_.isIOS?4:6:_.isIOS?5:7
}));
}),h.on(window,"unload",function(){
e||(e=!0,j.jsmonitor({
id:125350,
key:window.__second_open__?_.isIOS?8:10:_.isIOS?9:11
}));
});
}();
}();
var V=!1,W=!1;
});