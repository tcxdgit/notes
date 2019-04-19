# notes
笔记
"D:\Program Files\Anaconda3\python.exe" D:/PycharmProjects/data_process/translate_sogou.py
ad7e5d0b3db1c7322ca324dd5d91859b
<html><head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>URLè¿æ»¤</title>
<link href="../css/terminal.css" rel="stylesheet" type="text/css">

<script language="JavaScript" type="text/JavaScript">

// Added by csz in [2011-9-13] for the customize for malaysia: access denied page should show ip addr information etc.
var strShow = "According to the access control policy, you are not allowed to access this website. If you have any doubt, please contact the network administrator.";

function getParamString(name)
{
    var strHref = window.location.href;
	var intPos = strHref.indexOf("?");
    if(-1 == intPos)
    {
        return '';
    }
    
	var strRight = strHref.substr(intPos + 1);  // get the parameter from url
	var parameters = strRight.split("&"); 
	
    var pos, paraName, paraValue;
	
	for(var i=0; i<parameters.length; i++)
    {
        // get psoition of equality operator
        pos = parameters[i].indexOf('=');
        if(pos == -1)
        {
            continue;
        }
 
        // get name and value from url
        paraName = parameters[i].substring(0, pos);
        paraValue = parameters[i].substring(pos + 1);
 
        // if name search hit, then return current value. And restore + operator to blank space  
        if(paraName == name)
        {
            return decodeURIComponent(paraValue.replace(/\+/g, " "));
        }
    }
    
    return '';
}

function onInit()
{
    //var strIp   = getParamString("ip");
    var strType = getParamString("url_type");
    var strPlc  = getParamString("plc_name");
    
    if(strPlc.indexOf("#")>-1){
    	strPlc = strPlc.match(/(.*)#/)[1];
    }
    document.getElementById("strType").innerHTML = strType;
    document.getElementById("strPlc").innerHTML = strPlc;
}

</script></head>



<body onload="onInit()">
<div id="content">
  <h1 class="warning">è®¿é®è¢«æç»</h1>
  <div class="partition"> <span class="partition_left" style="width:220px;"></span> </div>
  <div name="ContentShow" id="ContentShow">
  	<p class="b_distance"><span lang="EN-US" style="letter-spacing: 0.05em; font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">1</span><span style="letter-spacing: 0.05em; font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">ï¼æ¬ä»£çæå¡å¨ï¼<span lang="EN-US">devproxy.h3c.com</span>ï¼çå®ä½æ¯æé«ç åå®éªå®¤<span lang="EN-US">/</span>åå¬åºå¯¹ä¸å¡å¼ºç¸å³çææ¯ç±»ç½ç«çè®¿é®æçï¼å¨ç åå®éªå®¤<span lang="EN-US">/</span>åå¬åºåè½è®¿é®ï¼æ¯å¯¹åæä»£çæå¡å¨<span lang="EN-US">proxy.h3c.com</span>çè¡¥åï¼ä½å¯¹å®å¨è¦æ±è¾é«ï¼ç®åä»å¼æ¾</span><b style="letter-spacing: 0.05em;"><span style="font-family: å¾®è½¯éé», sans-serif; color: red;">ä¸å¡å¼ºç¸å³çææ¯ç±»ç½ç«</span></b><span style="letter-spacing: 0.05em; font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">å¦<span lang="EN-US">github</span>ï¼æç´¢å¼æå¦<span lang="EN-US">google</span>ç­ãç»è¯ä¼°ææ°æ®å®å¨é£é©çç½ç«ï¼éææ¯ç±»çç½ç«ï¼å¦æ°é»ãå¨±ä¹ç±»ç­ï¼é½æ²¡æå¼æ¾ãç°è¿å¤äºå®éªå±é¶æ®µï¼åç»­<span lang="EN-US">IT</span>ä¼æ ¹æ®è¯ä¼°æåµéå½å¢å éææ¯ç±»å·¥ä½å¼ºç¸å³çç½ç«ã</span></p><p class="MsoNormal"><span lang="EN-US" style="font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">2</span><span style="font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">ï¼è¥å¨ç ååå¬åºï¼ä»å¯ä»¥éè¿ååç<span lang="EN-US">proxy.h3c.com</span>ä»£çè®¿é®äºèç½ã<span lang="EN-US"><o:p></o:p></span></span></p><p class="b_distance"><span style="letter-spacing: 0.05em; font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">3ï¼</span><span style="letter-spacing: 0.05em; font-family: å¾®è½¯éé», sans-serif; color: rgb(31, 73, 125);">è¥è®¿é®äºèç½è¦æ±æ²¡æéå¶ï¼åå¯ä»¥éè¿è¿ç¨æ¡é¢è®¿é®ç»¿äºçä¸ç½æ¡é¢<span lang="EN-US">webrds02.h3c.com</span>ãå°æ¥è¯¢ä¸è½½çèµæå¯ä»¥éè¿<span lang="EN-US">iPan.h3c.com</span>ä¼ å°æ¬å°ã</span></p><p class="b_distance"><br><b>å¦ææçé®ï¼è¯·èç³»ITç­çº¿<span lang="EN-US" style="letter-spacing: 0.05em; font-size: 10.5pt; font-family: å®ä½; color: rgb(31, 56, 100);">(0571-86760818</span><span style="letter-spacing: 0.05em; font-size: 10.5pt; font-family: å®ä½; color: rgb(31, 56, 100);">æ<span lang="EN-US">30818)</span></span></b><span style="letter-spacing: 0.05em;">ã</span></p></div>
</div>

</body></html>

Process finished with exit code 0
