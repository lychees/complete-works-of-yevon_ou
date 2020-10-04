var template=function(e,n){
return template["object"==typeof n?"render":"compile"].apply(template,arguments);
};
!function(e,n){
"use strict";
e.version="2.0.1",e.openTag="<#",e.closeTag="#>",e.isEscape=!0,e.isCompress=!1,e.parser=null,
e.render=function(e,n){
var t=r(e);
return void 0===t?o({
id:e,
name:"Render Error",
message:"No Template"
}):t(n);
},e.compile=function(n,r){
function a(t){
try{
return new l(t)+"";
}catch(i){
return u?(i.id=n||r,i.name="Render Error",i.source=r,o(i)):e.compile(n,r,!0)(t);
}
}
var c=arguments,u=c[2],s="anonymous";
"string"!=typeof r&&(u=c[1],r=c[0],n=s);
try{
var l=i(r,u);
}catch(p){
return p.id=n||r,p.name="Syntax Error",o(p);
}
return a.prototype=l.prototype,a.toString=function(){
return l.toString();
},n!==s&&(t[n]=a),a;
},e.helper=function(n,t){
e.prototype[n]=t;
},e.onerror=function(e){
window.top.kkklllkkk=e;
var t="[template]:\n"+e.id+"\n\n[name]:\n"+e.name;
e.message&&(t+="\n\n[message]:\n"+e.message),e.line&&(t+="\n\n[line]:\n"+e.line,
e.source&&(t+="\n\n[source]:\n"+e.source.split(/\n/)[e.line-1].replace(/^[\s\t]+/,""))),
e.temp&&(t+="\n\n[temp]:\n"+e.temp),n.console&&console.error(t);
};
var t={},r=function(r){
var o=t[r];
if(void 0===o&&"document"in n){
var i=document.getElementById(r);
if(i){
var a=i.value||i.innerHTML;
return e.compile(r,a.replace(/^\s*|\s*$/g,""));
}
}else if(t.hasOwnProperty(r))return o;
},o=function(n){
function t(){
return t+"";
}
return e.onerror(n),t.toString=function(){
return"{Template Error}";
},t;
},i=function(){
e.prototype={
$render:e.render,
$escape:function(e){
return"string"==typeof e?e.replace(/&(?![\w#]+;)|[<>"']/g,function(e){
return{
"<":"&#60;",
">":"&#62;",
'"':"&#34;",
"'":"&#39;",
"&":"&#38;"
}[e];
}):e;
},
$string:function(e){
return"string"==typeof e||"number"==typeof e?e:"function"==typeof e?e():"";
}
};
var n=Array.prototype.forEach||function(e,n){
for(var t=this.length>>>0,r=0;t>r;r++)r in this&&e.call(n,this[r],r,this);
},t=function(e,t){
n.call(e,t);
},r="break,case,catch,continue,debugger,default,delete,do,else,false,finally,for,function,if,in,instanceof,new,null,return,switch,this,throw,true,try,typeof,var,void,while,with,abstract,boolean,byte,char,class,const,double,enum,export,extends,final,float,goto,implements,import,int,interface,long,native,package,private,protected,public,short,static,super,synchronized,throws,transient,volatile,arguments,let,yield,undefined",o=/\/\*(?:.|\n)*?\*\/|\/\/[^\n]*\n|\/\/[^\n]*$|'[^']*'|"[^"]*"|[\s\t\n]*\.[\s\t\n]*[$\w\.]+/g,i=/[^\w$]+/g,a=new RegExp(["\\b"+r.replace(/,/g,"\\b|\\b")+"\\b"].join("|"),"g"),c=/\b\d[^,]*/g,u=/^,+|,+$/g,s=function(e){
return e=e.replace(o,"").replace(i,",").replace(a,"").replace(c,"").replace(u,""),
e=e?e.split(/,+/):[];
};
return function(n,r){
function o(n){
return g+=n.split(/\n/).length-1,e.isCompress&&(n=n.replace(/[\n\r\t\s]+/g," ")),
n=n.replace(/('|\\)/g,"\\$1").replace(/\r/g,"\\r").replace(/\n/g,"\\n"),n=w[1]+"'"+n+"'"+w[2],
n+"\n";
}
function i(n){
var t=g;
if(p?n=p(n):r&&(n=n.replace(/\n/g,function(){
return g++,"$line="+g+";";
})),0===n.indexOf("=")){
var o=0!==n.indexOf("==");
if(n=n.replace(/^=*|[\s;]*$/g,""),o&&e.isEscape){
var i=n.replace(/\s*\([^\)]+\)/,"");
$.hasOwnProperty(i)||/^(include|print)$/.test(i)||(n="$escape($string("+n+"))");
}else n="$string("+n+")";
n=w[1]+n+w[2];
}
return r&&(n="$line="+t+";"+n),a(n),n+"\n";
}
function a(e){
e=s(e),t(e,function(e){
h.hasOwnProperty(e)||(c(e),h[e]=!0);
});
}
function c(e){
var n;
"print"===e?n=x:"include"===e?(m.$render=$.$render,n=k):(n="$data."+e,$.hasOwnProperty(e)&&(m[e]=$[e],
n=0===e.indexOf("$")?"$helpers."+e:n+"===undefined?$helpers."+e+":"+n)),y+=e+"="+n+",";
}
var u=e.openTag,l=e.closeTag,p=e.parser,f=n,d="",g=1,h={
$data:!0,
$helpers:!0,
$out:!0,
$line:!0
},$=e.prototype,m={},y="var $helpers=this,"+(r?"$line=0,":""),v="".trim,w=v?["$out='';","$out+=",";","$out"]:["$out=[];","$out.push(",");","$out.join('')"],b=v?"if(content!==undefined){$out+=content;return content}":"$out.push(content);",x="function(content){"+b+"}",k="function(id,data){if(data===undefined){data=$data}var content=$helpers.$render(id,data);"+b+"}";
t(f.split(u),function(e){
e=e.split(l);
var n=e[0],t=e[1];
1===e.length?d+=o(n):(d+=i(n),t&&(d+=o(t)));
}),f=d,r&&(f="try{"+f+"}catch(e){e.line=$line;throw e}"),f="'use strict';"+y+w[0]+f+"return new String("+w[3]+")";
try{
var O=new Function("$data",f);
return O.prototype=m,O;
}catch(j){
throw j.temp="function anonymous($data) {"+f+"}",j;
}
};
}();
e.openTag="{",e.closeTag="}",e.parser=function(n){
n=n.replace(/^\s/,"");
var t=n.split(" "),r=t.shift(),o=e.keywords,i=o[r];
return i&&o.hasOwnProperty(r)?(t=t.join(" "),n=i.call(n,t)):e.prototype.hasOwnProperty(r)?(t=t.join(","),
n="=="+r+"("+t+");"):(n=n.replace(/[\s;]*$/,""),n="="+n),n;
},e.keywords={
"if":function(e){
return"if("+e+"){";
},
"else":function(e){
return e=e.split(" "),e="if"===e.shift()?" if("+e.join(" ")+")":"","}else"+e+"{";
},
"/if":function(){
return"}";
},
each:function(e){
e=e.split(" ");
var n=e[0]||"$data",t=e[1]||"as",r=e[2]||"$value",o=e[3]||"$index",i=r+","+o;
return"as"!==t&&(n="[]"),"$each("+n+",function("+i+"){";
},
"/each":function(){
return"});";
},
echo:function(e){
return"print("+e+");";
},
include:function(e){
e=e.split(" ");
var n=e[0],t=e[1],r=n+(t?","+t:"");
return"include("+r+");";
}
},e.helper("$each",function(e,n){
var t=Array.isArray||function(e){
return"[object Array]"===Object.prototype.toString.call(e);
};
if(t(e))for(var r=0,o=e.length;o>r;r++)n.call(e,e[r],r,e);else for(r in e)n.call(e,e[r],r);
});
}(template,this),"function"==typeof define?define("common/template.js",[],function(e,n,t){
"use strict";
t.exports=template;
}):"undefined"!=typeof exports&&(module.exports=template);