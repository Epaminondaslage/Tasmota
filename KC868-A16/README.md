KC868-A16

Here is "KCS" firmware for KinCony KC868-A series (ESP32) board.
How to download and use, online guide: 

https://www.kincony.com/esp32-kcsv2-firmware.html



<html>
<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=Generator content="Microsoft Word 15 (filtered)">
<style>
<!--
 /* Font Definitions */
 @font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:Aptos;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin-top:0cm;
	margin-right:0cm;
	margin-bottom:8.0pt;
	margin-left:0cm;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Aptos",sans-serif;}
a:link, span.MsoHyperlink
	{color:#467886;
	text-decoration:underline;}
.MsoChpDefault
	{font-size:11.0pt;}
.MsoPapDefault
	{margin-bottom:8.0pt;
	line-height:107%;}
@page WordSection1
	{size:595.3pt 841.9pt;
	margin:70.85pt 3.0cm 70.85pt 3.0cm;}
div.WordSection1
	{page:WordSection1;}
 /* List Definitions */
 ol
	{margin-bottom:0cm;}
ul
	{margin-bottom:0cm;}
-->
</style>

</head>

<body lang=PT-BR link="#467886" vlink="#96607D" style='word-wrap:break-word'>

<div class=WordSection1>

<p class=MsoNormal><b><span lang=EN-US>how to use “KCS”v2 firmware for KinCony
ESP32 board</span></b></p>

<p class=MsoNormal>You are here:</p>

<ol style='margin-top:0cm' start=1 type=1>
 <li class=MsoNormal><a href="https://www.kincony.com/" title=Home>Home</a></li>
 <li class=MsoNormal><a href="https://www.kincony.com/user-guide"
     title="User Guide">User Guide</a></li>
 <li class=MsoNormal><span lang=EN-US>how to use “KCS”v2 firmware…</span></li>
</ol>

<p class=MsoNormal><span lang=EN-US>Note: This document use for KinCony smart
controller: KC868-AM ASR A2 A4 A4S A6 A8 A8M A8S A16 A16S E16S A32 A32M A64
A128 AG AK AI AIO AP</span></p>

<p class=MsoNormal><span lang=EN-US>if you want to read by PDF file, </span><a
href="https://www.kincony.com/images/user-guide/KCS_V2/KCS_user_guide_v2.0.pdf"><span
lang=EN-US>download user guide PDF file</span></a><span lang=EN-US>.</span></p>

<p class=MsoNormal><b><span lang=EN-US>1. Download “KCS” firmware to KinCony
KC868-A series board.</span></b></p>

<p class=MsoNormal><span lang=EN-US>a. Download “ESP32 download tool” from </span><a
href="https://www.kincony.com/wp-content/uploads/2022/08/flash_download_tool_3.9.2.zip"><span
lang=EN-US>https://www.kincony.com/wp-content/uploads/2022/08/flash_download_tool_3.9.2.zip</span></a><span
lang=EN-US> and firmware BIN file from </span><a
href="https://www.kincony.com/forum/forumdisplay.php?fid=40"><span lang=EN-US>KinCony
forum</span></a><span lang=EN-US>.<br>
b. Open “flash_download_tool_3.9.2.exe”,</span></p>

<p class=MsoNormal><span lang=EN-US>(if your PCB chip is ESP32-WROOM-32E/32UE)
chose “ESP32” and “develop” item.</span></p>

<p class=MsoNormal><img border=0 width=416 height=289 id="Imagem 144"
src="how%20to%20use_arquivos/image001.png" alt="esp32 download tool"></p>

<p class=MsoNormal><span lang=EN-US>(if your PCB chip is ESP32-S3-WROOM-1U)
chose “ESP32-S3” and workMode=“develop”&nbsp; loadMode: “usb” item.</span></p>

<p class=MsoNormal><img border=0 width=408 height=321 id="Imagem 143"
src="how%20to%20use_arquivos/image002.png" alt=esp32-s3></p>

<p class=MsoNormal><span lang=EN-US>c. Chose KCS v2 firmware BIN file and COM
port then begin download. Total 5 steps.</span></p>

<p class=MsoNormal><img border=0 width=508 height=697 id="Imagem 142"
src="how%20to%20use_arquivos/image003.png" alt="esp32 download tool"><span
lang=EN-US><br>
<b>2. Use ethernet cable or WiFi config setting.</b></span></p>

<p class=MsoNormal><span lang=EN-US>a. use ethernet cable connect board to your
router, make sure your computer also connect with same router, just all in one
local network.<br>
b. Power on of your board, you can use KinCony scan device tool to find output
board IP address.</span></p>

<p class=MsoNormal><a href="https://www.kincony.com/download/UDP_SCAN_LIST.zip"><span
lang=EN-US>https://www.kincony.com/download/KinCony-SCAN_Device.zip</span></a></p>

<p class=MsoNormal><img border=0 width=567 height=257 id="Imagem 141"
src="how%20to%20use_arquivos/image137.jpg" alt="scan device"></p>

<p class=MsoNormal><span lang=EN-US>Total 5 steps to find out IP address.</span></p>

<p class=MsoNormal><span lang=EN-US>Step-1: chose your computer network adapter
when you are using.</span></p>

<p class=MsoNormal><span lang=EN-US>Step-2: chose your computer IP address
item.</span></p>

<p class=MsoNormal><span lang=EN-US>Step-3: click “StartMonitorPort” button.</span></p>

<p class=MsoNormal><span lang=EN-US>Step-4: click “SCAN” button.</span></p>

<p class=MsoNormal><span lang=EN-US>Step-5: board’s ethernet or WiFi IP address
, ID and type name will be listed.</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>If you first time power on , you board will
be found by ethernet IP address. Because your WiFi is work as “AP” mode as
default. After you config your WiFi as “STA” mode, you will find out the WiFi
IP address by KinCony scan device tool.</span></p>

<p class=MsoNormal><span lang=EN-US>You can use ethernet IP address login by
web browser to config board setting.</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>Note: if you want config only by WiFi, when
power on, your computer will find the “AP” hotspot, WiFi signal named “board
name” + “ID”.</span></p>

<p class=MsoNormal><img border=0 width=403 height=660 id="Imagem 140"
src="how%20to%20use_arquivos/image006.png" alt=ap></p>

<p class=MsoNormal><span lang=EN-US>Let your computer connect to the “AP”, it’s
without password, after you connected, just use </span><a
href="http://192.168.4.1"><span lang=EN-US>http://192.168.4.1</span></a><span
lang=EN-US> to login by webpage.</span></p>

<p class=MsoNormal><span lang=EN-US>If you can’t see the “AP”, you can “hold
on” board’s function button (ESP32 GPIO0) &gt;10 seconds, then board will be
set to factory, default state is “AP”.</span></p>

<p class=MsoNormal><img border=0 width=516 height=490 id="Imagem 139"
src="how%20to%20use_arquivos/image007.png" alt="iot login"></p>

<p class=MsoNormal><span lang=EN-US>You can login webpage by ethernet IP or
WiFi IP. Here is sample login by ethernet IP address 192.168.1.200</span></p>

<p class=MsoNormal><span lang=EN-US>Login user name and password default are
“admin”&nbsp; “admin”</span></p>

<p class=MsoNormal><img border=0 width=566 height=384 id="Imagem 138"
src="how%20to%20use_arquivos/image138.jpg" alt="home page"></p>

<p class=MsoNormal><span lang=EN-US>You can see this home page. </span>Some
parameters are shown.</p>

<p class=MsoNormal><img border=0 width=567 height=401 id="Imagem 137"
src="how%20to%20use_arquivos/image139.jpg" alt="input webpage"></p>

<p class=MsoNormal><span lang=EN-US>Here is INPUT webpage. Set every digital
input port how to work with OUTPUT ports.</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>“Reverse Level”: if checked, the effective
level at the digital input port becomes inverted. Just digital input use by
“HIGH” or “LOW” level. Usually digital input port short with GND = trigger.</span></p>

<p class=MsoNormal><img border=0 width=566 height=388 id="Imagem 136"
src="how%20to%20use_arquivos/image140.jpg" alt="output type"></p>

<p class=MsoNormal>Here is OUTPUT webpage.</p>

<p class=MsoNormal><img border=0 width=554 height=402 id="Imagem 135"
src="how%20to%20use_arquivos/image014.png" alt="output type"></p>

<p class=MsoNormal><span lang=EN-US>“hold on”: keep the state after turn ON/OFF</span></p>

<p class=MsoNormal><span lang=EN-US>“delay”:&nbsp; after you turn ON digital
output, will auto turn OFF after a “delay time” you have preset.</span></p>

<p class=MsoNormal><span lang=EN-US>“jogging”: when hold on the INPUT with GND,
digital output is ON, release INPUT with GND, digital output will be OFF right
now.</span></p>

<p class=MsoNormal><img border=0 width=567 height=299 id="Imagem 134"
src="how%20to%20use_arquivos/image141.jpg" alt=interlock></p>

<p class=MsoNormal><span lang=EN-US>“Interlock group”: set interlock group for
digital output. If set to “0” , disable interlock function. If “Output1” set to
“1” and “Output2” set to “1” = Output1 and Output2 work with interlock. If
“Output3” set to “2” and “Output4” set to “2” = Output3 and Output4 work with
interlock. For example , KC868-A64 have 64 channel digital output, so total
will have 64/2=32 interlock groups.</span></p>

<p class=MsoNormal><img border=0 width=566 height=309 id="Imagem 133"
src="how%20to%20use_arquivos/image142.jpg" alt="rf 433"></p>

<p class=MsoNormal><span lang=EN-US>Here is RF webpage. It support “Learn” ,
“transmit”, “Delete” RF code. Support EV1527 or PT2262, PT2264 wireless remote
code.<br>
When press “Learn” blue button, begin study mode, wait for you press remote’s
button, it will show message:</span></p>

<p class=MsoNormal><img border=0 width=566 height=226 id="Imagem 132"
src="how%20to%20use_arquivos/image143.jpg" alt="rf 433"></p>

<p class=MsoNormal><span lang=EN-US>Then press one button of remote:</span></p>

<p class=MsoNormal><img border=0 width=566 height=425 id="Imagem 131"
src="how%20to%20use_arquivos/image144.jpg" alt="rf 433"></p>

<p class=MsoNormal><span lang=EN-US>If learn signal successful, will show:</span></p>

<p class=MsoNormal><img border=0 width=567 height=291 id="Imagem 130"
src="how%20to%20use_arquivos/image145.jpg" alt="rf 433"></p>

<p class=MsoNormal><span lang=EN-US>If learn signal failure or time out , will
show:</span></p>

<p class=MsoNormal><img border=0 width=567 height=266 id="Imagem 129"
src="how%20to%20use_arquivos/image146.jpg" alt="rf 433"></p>

<p class=MsoNormal><span lang=EN-US>After you learned signal, then it will be
saved on controller.</span></p>

<p class=MsoNormal><img border=0 width=566 height=454 id="Imagem 128"
src="how%20to%20use_arquivos/image147.jpg" alt="ir webpage"></p>

<p class=MsoNormal><span lang=EN-US>Here is IR webpage. It support “Learn” ,
“transmit”, “Delete” IR code. Such as TV, DVD, air conditioner, fans or other
IR devices.</span></p>

<p class=MsoNormal><span lang=EN-US>When press “Learn” blue button, begin study
mode, wait for you press IR remote’s button, it will show message:</span></p>

<p class=MsoNormal><img border=0 width=566 height=230 id="Imagem 127"
src="how%20to%20use_arquivos/image148.jpg" alt=ir></p>

<p class=MsoNormal><span lang=EN-US>Then press one button of remote:</span></p>

<p class=MsoNormal><img border=0 width=566 height=425 id="Imagem 126"
src="how%20to%20use_arquivos/image149.jpg" alt="ir remote"></p>

<p class=MsoNormal><span lang=EN-US>If learn signal successful, will show:</span></p>

<p class=MsoNormal><img border=0 width=567 height=277 id="Imagem 125"
src="how%20to%20use_arquivos/image150.jpg" alt="ir remote"></p>

<p class=MsoNormal><span lang=EN-US>If learn signal failure or time out , will
show:</span></p>

<p class=MsoNormal><img border=0 width=567 height=281 id="Imagem 124"
src="how%20to%20use_arquivos/image151.jpg" alt="ir remote"></p>

<p class=MsoNormal><span lang=EN-US>After you learned signal, then it will be
saved on controller.</span></p>

<p class=MsoNormal><img border=0 width=567 height=250 id="Imagem 123"
src="how%20to%20use_arquivos/image152.jpg" alt=ir></p>

<p class=MsoNormal><img border=0 width=566 height=453 id="Imagem 122"
src="how%20to%20use_arquivos/image153.jpg" alt=sensor></p>

<p class=MsoNormal><span lang=EN-US>Here is sensor webpage. You can set
different sensor model for 1-wire GPIO ports.</span></p>

<p class=MsoNormal><span lang=EN-US>Temperature Threshold:</span></p>

<p class=MsoNormal><span lang=EN-US>If the preset difference is exceeded,
temperature data will be auto updated.</span></p>

<p class=MsoNormal><span lang=EN-US>For example: “Temperature Threshold”
=2&nbsp; now temperature is 28°C, so next time , when new temperature is
&gt;30°C(28+2) or &lt;26°C(28-2) will update.</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>Humidity Threshold:</span></p>

<p class=MsoNormal><span lang=EN-US>If the preset difference is exceeded,
humidity data will be auto updated.</span></p>

<p class=MsoNormal><span lang=EN-US>For example: “Humidity Threshold” =10&nbsp;
now humidity is 75%, so next time , when new humidity is &gt;85%(75+10) or
&lt;65%(75-10) will update.</span></p>

<p class=MsoNormal><img border=0 width=566 height=603 id="Imagem 121"
src="how%20to%20use_arquivos/image154.jpg" alt="iot monitor"></p>

<p class=MsoNormal>Here is monitor webpage.</p>

<p class=MsoNormal><img border=0 width=566 height=66 id="Imagem 120"
src="how%20to%20use_arquivos/image155.jpg" alt="protocol monitor"></p>

<p class=MsoNormal><span lang=EN-US>Monitor all protocol work state, whether
have connect to server or have a client have connected.</span></p>

<p class=MsoNormal><img border=0 width=566 height=167 id="Imagem 119"
src="how%20to%20use_arquivos/image156.jpg" alt=adc></p>

<p class=MsoNormal><span lang=EN-US>Monitor ADC value.</span></p>

<p class=MsoNormal><span lang=EN-US>In order to easily view the values of each
sensor, we can set a separate sensor channel name, range, display unit, and
automatically reported threshold for each sensor.</span></p>

<p class=MsoNormal><span lang=EN-US>Just click “gear” image, will show the
config page.</span></p>

<p class=MsoNormal><img border=0 width=566 height=385 id="Imagem 118"
src="how%20to%20use_arquivos/image157.jpg" alt="adc setting"></p>

<p class=MsoNormal><span lang=EN-US>Fox example, we set a water level analog
sensor, name is “water level”, unit is M (meter), Custom value1 and value2
means: if you are using DC 0-5v analog sensor, when sensor voltage is 0v,
what’s “Custom value1” corresponding value. when sensor voltage is 5v, what’s
“Custom value2” corresponding value.</span></p>

<p class=MsoNormal>So sensor dc 0-5v — convert à 0-3 meter</p>

<p class=MsoNormal><span lang=EN-US>If you are using sensor 4-20mA, so 4-20mA
4mA=Custom value1, 20mA is Custom value2.</span></p>

<p class=MsoNormal><img border=0 width=567 height=138 id="Imagem 117"
src="how%20to%20use_arquivos/image158.jpg" alt=adc></p>

<p class=MsoNormal><span lang=EN-US>Then you will see the actually sensor name
, value and unit on the monitor webpage.</span></p>

<p class=MsoNormal><img border=0 width=566 height=226 id="Imagem 116"
src="how%20to%20use_arquivos/image159.jpg" alt="input rename"></p>

<p class=MsoNormal><span lang=EN-US>Double click on the input name’s TEXT can
be rename by yourself.</span></p>

<p class=MsoNormal><img border=0 width=567 height=244 id="Imagem 115"
src="how%20to%20use_arquivos/image160.jpg" alt=rename></p>

<p class=MsoNormal>After renamed.</p>

<p class=MsoNormal><img border=0 width=567 height=273 id="Imagem 114"
src="how%20to%20use_arquivos/image161.jpg" alt="output rename"></p>

<p class=MsoNormal><span lang=EN-US>Use the same way (double click TEXT) can
rename of the output ports.</span></p>

<p class=MsoNormal><img border=0 width=566 height=398 id="Imagem 113"
src="how%20to%20use_arquivos/image162.jpg" alt="monitor sensor state"></p>

<p class=MsoNormal><span lang=EN-US>Green ico for INPUT means triggered.</span></p>

<p class=MsoNormal><span lang=EN-US>Green ico for OUTPUT means output is ON
state.</span></p>

<p class=MsoNormal><img border=0 width=567 height=470 id="Imagem 112"
src="how%20to%20use_arquivos/image163.jpg" alt=ifttt></p>

<p class=MsoNormal><span lang=EN-US>Here is IFTTT webpage. It can create IFTTT
AUTOMATION. Press “Run” blue button for running testing. </span>Press “Edit”
yellow button for modify.</p>

<p class=MsoNormal><img border=0 width=567 height=446 id="Imagem 111"
src="how%20to%20use_arquivos/image164.jpg" alt=ifttt></p>

<p class=MsoNormal><img border=0 width=567 height=248 id="Imagem 110"
src="how%20to%20use_arquivos/image165.jpg" alt=ifttt></p>

<p class=MsoNormal><span lang=EN-US>If your board support 4G SIM7600 module,
there will have “SMS” and “voice call” ICO.</span></p>

<p class=MsoNormal><span lang=EN-US>You can rename the AUTOMATION name. </span>“enable”
or “disable” it.</p>

<p class=MsoNormal><img border=0 width=567 height=305 id="Imagem 109"
src="how%20to%20use_arquivos/image166.jpg" alt=ifttt></p>

<p class=MsoNormal>DI options:</p>

<p class=MsoNormal><img border=0 width=566 height=290 id="Imagem 108"
src="how%20to%20use_arquivos/image167.jpg" alt=ifttt></p>

<p class=MsoNormal>AI options:</p>

<p class=MsoNormal><img border=0 width=566 height=362 id="Imagem 107"
src="how%20to%20use_arquivos/image168.jpg" alt=ifttt></p>

<p class=MsoNormal>RF options:</p>

<p class=MsoNormal><img border=0 width=567 height=363 id="Imagem 106"
src="how%20to%20use_arquivos/image169.jpg" alt=ifttt></p>

<p class=MsoNormal>Sensor options:</p>

<p class=MsoNormal><img border=0 width=567 height=387 id="Imagem 105"
src="how%20to%20use_arquivos/image170.jpg" alt=ifttt></p>

<p class=MsoNormal><span lang=EN-US>Timer options:</span></p>

<p class=MsoNormal><span lang=EN-US>If your board support 4G SIM7600 module,
there will have “SMS” and “voice call” options:</span></p>

<p class=MsoNormal><img border=0 width=567 height=274 id="Imagem 104"
src="how%20to%20use_arquivos/image171.jpg" alt=ifttt></p>

<p class=MsoNormal>SMS options:</p>

<p class=MsoNormal><img border=0 width=567 height=268 id="Imagem 103"
src="how%20to%20use_arquivos/image172.jpg" alt=ifttt></p>

<p class=MsoNormal>Voice call options:</p>

<p class=MsoNormal><img border=0 width=567 height=442 id="Imagem 102"
src="how%20to%20use_arquivos/image173.jpg" alt=ifttt></p>

<p class=MsoNormal><span lang=EN-US>If enable [logical “AND”] option, All IF
conditions need to be met before the action can be executed. </span>If
“disable” just All IF conditions is “OR” logical.</p>

<p class=MsoNormal><img border=0 width=567 height=350 id="Imagem 101"
src="how%20to%20use_arquivos/image174.jpg" alt=ifttt></p>

<p class=MsoNormal><span lang=EN-US>DO options:</span></p>

<p class=MsoNormal><span lang=EN-US>you can set and separated by a “space”. You
can enter “1 2 3 4 5” or “1-5” in the corresponding option to do something of
digital output No.1-5</span></p>

<p class=MsoNormal><img border=0 width=567 height=326 id="Imagem 100"
src="how%20to%20use_arquivos/image175.jpg" alt=ifttt><span lang=EN-US><br>
Fox example:</span></p>

<p class=MsoNormal><span lang=EN-US>The config photo that means:</span></p>

<p class=MsoNormal><span lang=EN-US>Turn ON digital output 1,2,3,</span></p>

<p class=MsoNormal><span lang=EN-US>Turn OFF digital output 4,5,6</span></p>

<p class=MsoNormal>Toggle digital output
7,9,10,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32</p>

<p class=MsoNormal><img border=0 width=566 height=352 id="Imagem 99"
src="how%20to%20use_arquivos/image176.jpg" alt=ifttt></p>

<p class=MsoNormal>AO options:</p>

<p class=MsoNormal><img border=0 width=567 height=354 id="Imagem 98"
src="how%20to%20use_arquivos/image177.jpg" alt=ifttt></p>

<p class=MsoNormal>RF options:</p>

<p class=MsoNormal><img border=0 width=567 height=354 id="Imagem 97"
src="how%20to%20use_arquivos/image178.jpg" alt=ifttt></p>

<p class=MsoNormal>IR options:</p>

<p class=MsoNormal><img border=0 width=567 height=343 id="Imagem 96"
src="how%20to%20use_arquivos/image179.jpg" alt=ifttt></p>

<p class=MsoNormal>Delay options:</p>

<p class=MsoNormal><img border=0 width=567 height=352 id="Imagem 95"
src="how%20to%20use_arquivos/image180.jpg" alt=ifttt></p>

<p class=MsoNormal>Custom protocol options:</p>

<p class=MsoNormal><img border=0 width=566 height=331 id="Imagem 94"
src="how%20to%20use_arquivos/image181.jpg" alt="ifttt sms"></p>

<p class=MsoNormal>SMS options:</p>

<p class=MsoNormal><img border=0 width=566 height=229 id="Imagem 93"
src="how%20to%20use_arquivos/image182.jpg" alt="ifttt call"></p>

<p class=MsoNormal>Voice call options:</p>

<p class=MsoNormal><img border=0 width=567 height=558 id="Imagem 92"
src="how%20to%20use_arquivos/image183.jpg" alt=ifttt></p>

<p class=MsoNormal><span lang=EN-US>After create completed, you can see all IF
and THEN ICO, you can “Save” the AUTOMATION – “scene1” or click small ICO for
modify again.</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><img border=0 width=566 height=701 id="Imagem 91"
src="how%20to%20use_arquivos/image184.jpg" alt="network setting"></p>

<p class=MsoNormal><span lang=EN-US>Network setting for ethernet and WiFi.</span></p>

<p class=MsoNormal><span lang=EN-US>You if set WiFi by AP mode. device such as
mobile phone or tablet can connect to board by wifi directly without wifi
router.</span></p>

<p class=MsoNormal><img border=0 width=457 height=315 id="Imagem 90"
src="how%20to%20use_arquivos/image103.png" alt=sta></p>

<p class=MsoNormal><span lang=EN-US>If you set WiFi to STA mode, also you have
connect to router by ethernet cable. Board will use ethernet firstly, if
ethernet cable disconnected, then will auto switch to WiFi connect to your wifi
router, so that make sure let board always connect to your router.</span></p>

<p class=MsoNormal><img border=0 width=566 height=474 id="Imagem 89"
src="how%20to%20use_arquivos/image185.jpg" alt="gprs setting"></p>

<p class=MsoNormal><span lang=EN-US>Here is Network – GSM webpage.</span></p>

<p class=MsoNormal><span lang=EN-US>You can enable/disable your GSM module. If
disabled, SMS, voice call, GPRS will not work. MAX support fill 6 Administrator
Phone Numbers. Only these 6 mobile phone number can use SMS and voice call
function. </span>Tuya app with GPRS no mobile phone number limit.</p>

<p class=MsoNormal><img border=0 width=566 height=238 id="Imagem 88"
src="how%20to%20use_arquivos/image186.jpg" alt="gsm test"></p>

<p class=MsoNormal><span lang=EN-US>You can select your phone number, then
click “Send a message” or “Make a call” for a test.</span></p>

<p class=MsoNormal><img border=0 width=567 height=486 id="Imagem 87"
src="how%20to%20use_arquivos/image187.jpg" alt="esp32 sms"></p>

<p class=MsoNormal><span lang=EN-US>You can define your SMS content use for IF
condition. SMS can define by your local language, not only English.</span></p>

<p class=MsoNormal><img border=0 width=567 height=493 id="Imagem 86"
src="how%20to%20use_arquivos/image188.jpg" alt="esp32 sms"></p>

<p class=MsoNormal><span lang=EN-US>You can define your SMS content use for
THEN actions, such as alarm notification. SMS can define by your local
language, not only English.</span></p>

<p class=MsoNormal><img border=0 width=567 height=496 id="Imagem 85"
src="how%20to%20use_arquivos/image189.jpg" alt="phone relay"></p>

<p class=MsoNormal><span lang=EN-US>You can define voice call control (DTMF
code) for IF condition.</span></p>

<p class=MsoNormal><span lang=EN-US>For example: when you voice call your
board, when it connected, press key 10# for turn ON relay-1 or press 11# for
turn OFF relay-2. </span>Just define a number end with “#”.</p>

<p class=MsoNormal><img border=0 width=566 height=916 id="Imagem 84"
src="how%20to%20use_arquivos/image190.jpg" alt=protocol></p>

<p class=MsoNormal><img border=0 width=567 height=170 id="Imagem 83"
src="how%20to%20use_arquivos/image191.jpg" alt="RS485 protocol"></p>

<p class=MsoNormal><span lang=EN-US>Here is protocol setting webpage. You can
enable/disable different protocol in webpage. About these protocol document you
can download from KinCony’s webpage.</span></p>

<p class=MsoNormal><img border=0 width=566 height=661 id="Imagem 82"
src="how%20to%20use_arquivos/image118.png" alt="tuya protocol"></p>

<p class=MsoNormal><span lang=EN-US>If you want to use Tuya mobile phone
application by remote monitor and control output by internet. You can contact
us order the Tuya licence code. If you bought Tuya licence from KinCony, you
just fill product id, device id, device secret, bind code to this webpage, then
it will auto generate QR code, you can scan QR code add board to Tuya mobile
phone application.</span></p>

<p class=MsoNormal><span lang=EN-US>If your board have 4G SIM7600 module, you
can use Tuya app by GPRS. </span>Just enable it for Tuya.</p>

<p class=MsoNormal><img border=0 width=566 height=578 id="Imagem 81"
src="how%20to%20use_arquivos/image192.jpg" alt="tuya app"></p>

<p class=MsoNormal><img border=0 width=566 height=350 id="Imagem 80"
src="how%20to%20use_arquivos/image193.jpg" alt="custom protocol"></p>

<p class=MsoNormal><span lang=EN-US>Here is custom protocols webpage.</span></p>

<p class=MsoNormal><span lang=EN-US>You can create message for TCP Client, UDP
Client, RS232, RS485, HTTP GET, HTTP POST different ways.</span></p>

<p class=MsoNormal><span lang=EN-US>If “HEX” options is not checked, will send
message by ANSI String.</span></p>

<p class=MsoNormal><span lang=EN-US>Fox example:</span></p>

<p class=MsoNormal><span lang=EN-US>If you want send a TCP string command to
another relay module to turn ON relay1:</span></p>

<p class=MsoNormal><img border=0 width=567 height=211 id="Imagem 79"
src="how%20to%20use_arquivos/image194.jpg" alt="custom protocol tcp"></p>

<p class=MsoNormal><img border=0 width=567 height=463 id="Imagem 78"
src="how%20to%20use_arquivos/image195.jpg" alt="tcp client"></p>

<p class=MsoNormal><span lang=EN-US>Make sure have enabled TCP Client protocol,
remote address: 192.168.1.215 port: 4196 is another relay board.</span></p>

<p class=MsoNormal><span lang=EN-US>So the string “RELAY-SET-255,1,1” will send
to IP:192.168.1.215 port: 4196 device by TCP.</span></p>

<p class=MsoNormal>Fox example:</p>

<p class=MsoNormal><img border=0 width=566 height=132 id="Imagem 77"
src="how%20to%20use_arquivos/image196.jpg"
alt="Interface gráfica do usuário, Aplicativo&#10;&#10;Descrição gerada automaticamente"></p>

<p class=MsoNormal><span lang=EN-US>This means:</span></p>

<p class=MsoNormal><span lang=EN-US>send HTTP command string</span></p>

<p class=MsoNormal><span lang=EN-US>“http://192.168.1.200/sw_ctl.cgi?Relay01=ON&amp;postpwd=abcd”
by HTTP GET way. If you need add some message with HTTP command, just fill the
“Message” edit box.</span></p>

<p class=MsoNormal><img border=0 width=566 height=446 id="Imagem 76"
src="how%20to%20use_arquivos/image197.jpg"
alt="Interface gráfica do usuário, Aplicativo&#10;&#10;Descrição gerada automaticamente"></p>

<p class=MsoNormal><span lang=EN-US>Make sure you can enable the “HTTP Server”
protocol and set the “request secret” for safety.</span></p>

<p class=MsoNormal><img border=0 width=566 height=135 id="Imagem 75"
src="how%20to%20use_arquivos/image198.jpg" alt=rs485></p>

<p class=MsoNormal><span lang=EN-US>If you board have RS485, then the option
will list “RS485”.</span></p>

<p class=MsoNormal><img border=0 width=567 height=610 id="Imagem 74"
src="how%20to%20use_arquivos/image199.jpg" alt=system></p>

<p class=MsoNormal><span lang=EN-US>Here is system webpage.</span></p>

<p class=MsoNormal><span lang=EN-US>“keep output after restart”: when after
power failure, whether auto recovery digital output state when power on again.</span></p>

<p class=MsoNormal><span lang=EN-US>“auto send ADC values”: every 5 seconds
auto feedback analog input ports value by protocol.</span></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

<p class=MsoNormal><span lang=EN-US>“double click time”: adjust value for
change speed of double click.</span></p>

<p class=MsoNormal><span lang=EN-US>“hold on time”: adjust value for long or
short the hold on time.</span></p>

<p class=MsoNormal><img border=0 width=566 height=573 id="Imagem 73"
src="how%20to%20use_arquivos/image200.jpg" alt="system reboot"></p>

<p class=MsoNormal><span lang=EN-US>“Restart Board”: reboot board.</span></p>

<p class=MsoNormal><span lang=EN-US>“Restore Factory”: clear all setting and
set WiFi to “AP” mode.</span></p>

<p class=MsoNormal><span lang=EN-US>Category:&nbsp;</span><a
href="https://www.kincony.com/user-guide"><span lang=EN-US>User Guide</span></a><a
href="https://www.kincony.com/author/kinconyadminuu"
title="View all posts by admin"><span lang=EN-US>By admin</span></a><a
href="https://www.kincony.com/2023/07/20" title="am8:15"><span lang=EN-US>07/20/2023</span></a></p>

<p class=MsoNormal><b><span lang=EN-US>Author:&nbsp;admin</span></b></p>

<p class=MsoNormal><span lang=EN-US>&nbsp;</span></p>

</div>

</body>

</html>
