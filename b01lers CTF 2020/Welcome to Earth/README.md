# b01lers CTF 2020 – Welcome to Earth

* **Category:** web
* **Points:** 100

## Challenge

> This was supposed to be my weekend off, but noooo, you got me out here, draggin' your heavy ass through the burning desert, with your dreadlocks sticking out the back of my parachute. You gotta come down here with an attitude, actin' all big and bad. And what the hell is that smell? I coulda been at a barbecue, but I ain't mad.
> 
> http://web.ctf.b01lers.com:1000/

## Solution

The webpage contains the following HTML.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
  </head>
  <body>
    <h1>AMBUSH!</h1>
    <p>You've gotta escape!</p>
    <img src="/static/img/f18.png" alt="alien mothership" style="width:60vw;" />
    <script>
      document.onkeydown = function(event) {
        event = event || window.event;
        if (event.keyCode == 27) {
          event.preventDefault();
          window.location = "/chase/";
        } else die();
      };

      function sleep(ms) {
        return new Promise(resolve => setTimeout(resolve, ms));
      }

      async function dietimer() {
        await sleep(10000);
        die();
      }

      function die() {
        window.location = "/die/";
      }

      dietimer();
    </script>
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/chase/` endpoint.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
  </head>
  <body>
    <h1>CHASE!</h1>
    <p>
      You managed to chase one of the enemy fighters, but there's a wall coming
      up fast!
    </p>
    <button onclick="left()">Left</button>
    <button onclick="right()">Right</button>

    <img
      src="/static/img/Canyon_Chase_16.png"
      alt="canyon chase"
      style="width:60vw;"
    />
    <script>
      function sleep(ms) {
        return new Promise(resolve => setTimeout(resolve, ms));
      }

      async function dietimer() {
        await sleep(1000);
        die();
      }

      function die() {
        window.location = "/die/";
      }

      function left() {
        window.location = "/die/";
      }

      function leftt() {
        window.location = "/leftt/";
      }

      function right() {
        window.location = "/die/";
      }

      dietimer();
    </script>
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/leftt/` endpoint.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
  </head>
  <body>
    <h1>SHOOT IT</h1>
    <p>You've got the bogey in your sights, take the shot!</p>
    <img
      src="/static/img/locked.png"
      alt="locked on"
      style="width:60vw;"
    />
    </br>
    <button onClick="window.location='/die/'">Take the shot</button>
    <!-- <button onClick="window.location='/shoot/'">Take the shot</button> -->
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/shoot/` endpoint.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
  </head>
  <body>
    <h1>YOU SHOT IT DOWN!</h1>
    <p>Well done! You also crash in the process</p>
    <img src="/static/img/parachute.png" alt="parachute" style="width:60vw;" />
    <button onClick="window.location='/door/'">Continue</button>
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/door/` endpoint.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
    <script src="/static/js/door.js"></script>
  </head>
  <body>
    <h1>YOU APPROACH THE ALIEN CRAFT!</h1>
    <p>How do you get inside?</p>
    <img src="/static/img/ship.png" alt="crashed ship" style="width:60vw;" />
    <form id="door_form">
      <input type="radio" name="side" value="0" />0
      <input type="radio" name="side" value="1" />1
      <input type="radio" name="side" value="2" />2
      <input type="radio" name="side" value="3" />3
      <input type="radio" name="side" value="4" />4
      <input type="radio" name="side" value="5" />5
      <input type="radio" name="side" value="6" />6
      <input type="radio" name="side" value="7" />7
      <input type="radio" name="side" value="8" />8
      <input type="radio" name="side" value="9" />9
      <input type="radio" name="side" value="10" />10
      <input type="radio" name="side" value="11" />11
      <input type="radio" name="side" value="12" />12
      <input type="radio" name="side" value="13" />13
      <input type="radio" name="side" value="14" />14
      <input type="radio" name="side" value="15" />15
      <input type="radio" name="side" value="16" />16
      <input type="radio" name="side" value="17" />17
      <input type="radio" name="side" value="18" />18
      <input type="radio" name="side" value="19" />19
      <input type="radio" name="side" value="20" />20
      <input type="radio" name="side" value="21" />21
      <input type="radio" name="side" value="22" />22
      <input type="radio" name="side" value="23" />23
      <input type="radio" name="side" value="24" />24
      <input type="radio" name="side" value="25" />25
      <input type="radio" name="side" value="26" />26
      <input type="radio" name="side" value="27" />27
      <input type="radio" name="side" value="28" />28
      <input type="radio" name="side" value="29" />29
      <input type="radio" name="side" value="30" />30
      <input type="radio" name="side" value="31" />31
      <input type="radio" name="side" value="32" />32
      <input type="radio" name="side" value="33" />33
      <input type="radio" name="side" value="34" />34
      <input type="radio" name="side" value="35" />35
      <input type="radio" name="side" value="36" />36
      <input type="radio" name="side" value="37" />37
      <input type="radio" name="side" value="38" />38
      <input type="radio" name="side" value="39" />39
      <input type="radio" name="side" value="40" />40
      <input type="radio" name="side" value="41" />41
      <input type="radio" name="side" value="42" />42
      <input type="radio" name="side" value="43" />43
      <input type="radio" name="side" value="44" />44
      <input type="radio" name="side" value="45" />45
      <input type="radio" name="side" value="46" />46
      <input type="radio" name="side" value="47" />47
      <input type="radio" name="side" value="48" />48
      <input type="radio" name="side" value="49" />49
      <input type="radio" name="side" value="50" />50
      <input type="radio" name="side" value="51" />51
      <input type="radio" name="side" value="52" />52
      <input type="radio" name="side" value="53" />53
      <input type="radio" name="side" value="54" />54
      <input type="radio" name="side" value="55" />55
      <input type="radio" name="side" value="56" />56
      <input type="radio" name="side" value="57" />57
      <input type="radio" name="side" value="58" />58
      <input type="radio" name="side" value="59" />59
      <input type="radio" name="side" value="60" />60
      <input type="radio" name="side" value="61" />61
      <input type="radio" name="side" value="62" />62
      <input type="radio" name="side" value="63" />63
      <input type="radio" name="side" value="64" />64
      <input type="radio" name="side" value="65" />65
      <input type="radio" name="side" value="66" />66
      <input type="radio" name="side" value="67" />67
      <input type="radio" name="side" value="68" />68
      <input type="radio" name="side" value="69" />69
      <input type="radio" name="side" value="70" />70
      <input type="radio" name="side" value="71" />71
      <input type="radio" name="side" value="72" />72
      <input type="radio" name="side" value="73" />73
      <input type="radio" name="side" value="74" />74
      <input type="radio" name="side" value="75" />75
      <input type="radio" name="side" value="76" />76
      <input type="radio" name="side" value="77" />77
      <input type="radio" name="side" value="78" />78
      <input type="radio" name="side" value="79" />79
      <input type="radio" name="side" value="80" />80
      <input type="radio" name="side" value="81" />81
      <input type="radio" name="side" value="82" />82
      <input type="radio" name="side" value="83" />83
      <input type="radio" name="side" value="84" />84
      <input type="radio" name="side" value="85" />85
      <input type="radio" name="side" value="86" />86
      <input type="radio" name="side" value="87" />87
      <input type="radio" name="side" value="88" />88
      <input type="radio" name="side" value="89" />89
      <input type="radio" name="side" value="90" />90
      <input type="radio" name="side" value="91" />91
      <input type="radio" name="side" value="92" />92
      <input type="radio" name="side" value="93" />93
      <input type="radio" name="side" value="94" />94
      <input type="radio" name="side" value="95" />95
      <input type="radio" name="side" value="96" />96
      <input type="radio" name="side" value="97" />97
      <input type="radio" name="side" value="98" />98
      <input type="radio" name="side" value="99" />99
      <input type="radio" name="side" value="100" />100
      <input type="radio" name="side" value="101" />101
      <input type="radio" name="side" value="102" />102
      <input type="radio" name="side" value="103" />103
      <input type="radio" name="side" value="104" />104
      <input type="radio" name="side" value="105" />105
      <input type="radio" name="side" value="106" />106
      <input type="radio" name="side" value="107" />107
      <input type="radio" name="side" value="108" />108
      <input type="radio" name="side" value="109" />109
      <input type="radio" name="side" value="110" />110
      <input type="radio" name="side" value="111" />111
      <input type="radio" name="side" value="112" />112
      <input type="radio" name="side" value="113" />113
      <input type="radio" name="side" value="114" />114
      <input type="radio" name="side" value="115" />115
      <input type="radio" name="side" value="116" />116
      <input type="radio" name="side" value="117" />117
      <input type="radio" name="side" value="118" />118
      <input type="radio" name="side" value="119" />119
      <input type="radio" name="side" value="120" />120
      <input type="radio" name="side" value="121" />121
      <input type="radio" name="side" value="122" />122
      <input type="radio" name="side" value="123" />123
      <input type="radio" name="side" value="124" />124
      <input type="radio" name="side" value="125" />125
      <input type="radio" name="side" value="126" />126
      <input type="radio" name="side" value="127" />127
      <input type="radio" name="side" value="128" />128
      <input type="radio" name="side" value="129" />129
      <input type="radio" name="side" value="130" />130
      <input type="radio" name="side" value="131" />131
      <input type="radio" name="side" value="132" />132
      <input type="radio" name="side" value="133" />133
      <input type="radio" name="side" value="134" />134
      <input type="radio" name="side" value="135" />135
      <input type="radio" name="side" value="136" />136
      <input type="radio" name="side" value="137" />137
      <input type="radio" name="side" value="138" />138
      <input type="radio" name="side" value="139" />139
      <input type="radio" name="side" value="140" />140
      <input type="radio" name="side" value="141" />141
      <input type="radio" name="side" value="142" />142
      <input type="radio" name="side" value="143" />143
      <input type="radio" name="side" value="144" />144
      <input type="radio" name="side" value="145" />145
      <input type="radio" name="side" value="146" />146
      <input type="radio" name="side" value="147" />147
      <input type="radio" name="side" value="148" />148
      <input type="radio" name="side" value="149" />149
      <input type="radio" name="side" value="150" />150
      <input type="radio" name="side" value="151" />151
      <input type="radio" name="side" value="152" />152
      <input type="radio" name="side" value="153" />153
      <input type="radio" name="side" value="154" />154
      <input type="radio" name="side" value="155" />155
      <input type="radio" name="side" value="156" />156
      <input type="radio" name="side" value="157" />157
      <input type="radio" name="side" value="158" />158
      <input type="radio" name="side" value="159" />159
      <input type="radio" name="side" value="160" />160
      <input type="radio" name="side" value="161" />161
      <input type="radio" name="side" value="162" />162
      <input type="radio" name="side" value="163" />163
      <input type="radio" name="side" value="164" />164
      <input type="radio" name="side" value="165" />165
      <input type="radio" name="side" value="166" />166
      <input type="radio" name="side" value="167" />167
      <input type="radio" name="side" value="168" />168
      <input type="radio" name="side" value="169" />169
      <input type="radio" name="side" value="170" />170
      <input type="radio" name="side" value="171" />171
      <input type="radio" name="side" value="172" />172
      <input type="radio" name="side" value="173" />173
      <input type="radio" name="side" value="174" />174
      <input type="radio" name="side" value="175" />175
      <input type="radio" name="side" value="176" />176
      <input type="radio" name="side" value="177" />177
      <input type="radio" name="side" value="178" />178
      <input type="radio" name="side" value="179" />179
      <input type="radio" name="side" value="180" />180
      <input type="radio" name="side" value="181" />181
      <input type="radio" name="side" value="182" />182
      <input type="radio" name="side" value="183" />183
      <input type="radio" name="side" value="184" />184
      <input type="radio" name="side" value="185" />185
      <input type="radio" name="side" value="186" />186
      <input type="radio" name="side" value="187" />187
      <input type="radio" name="side" value="188" />188
      <input type="radio" name="side" value="189" />189
      <input type="radio" name="side" value="190" />190
      <input type="radio" name="side" value="191" />191
      <input type="radio" name="side" value="192" />192
      <input type="radio" name="side" value="193" />193
      <input type="radio" name="side" value="194" />194
      <input type="radio" name="side" value="195" />195
      <input type="radio" name="side" value="196" />196
      <input type="radio" name="side" value="197" />197
      <input type="radio" name="side" value="198" />198
      <input type="radio" name="side" value="199" />199
      <input type="radio" name="side" value="200" />200
      <input type="radio" name="side" value="201" />201
      <input type="radio" name="side" value="202" />202
      <input type="radio" name="side" value="203" />203
      <input type="radio" name="side" value="204" />204
      <input type="radio" name="side" value="205" />205
      <input type="radio" name="side" value="206" />206
      <input type="radio" name="side" value="207" />207
      <input type="radio" name="side" value="208" />208
      <input type="radio" name="side" value="209" />209
      <input type="radio" name="side" value="210" />210
      <input type="radio" name="side" value="211" />211
      <input type="radio" name="side" value="212" />212
      <input type="radio" name="side" value="213" />213
      <input type="radio" name="side" value="214" />214
      <input type="radio" name="side" value="215" />215
      <input type="radio" name="side" value="216" />216
      <input type="radio" name="side" value="217" />217
      <input type="radio" name="side" value="218" />218
      <input type="radio" name="side" value="219" />219
      <input type="radio" name="side" value="220" />220
      <input type="radio" name="side" value="221" />221
      <input type="radio" name="side" value="222" />222
      <input type="radio" name="side" value="223" />223
      <input type="radio" name="side" value="224" />224
      <input type="radio" name="side" value="225" />225
      <input type="radio" name="side" value="226" />226
      <input type="radio" name="side" value="227" />227
      <input type="radio" name="side" value="228" />228
      <input type="radio" name="side" value="229" />229
      <input type="radio" name="side" value="230" />230
      <input type="radio" name="side" value="231" />231
      <input type="radio" name="side" value="232" />232
      <input type="radio" name="side" value="233" />233
      <input type="radio" name="side" value="234" />234
      <input type="radio" name="side" value="235" />235
      <input type="radio" name="side" value="236" />236
      <input type="radio" name="side" value="237" />237
      <input type="radio" name="side" value="238" />238
      <input type="radio" name="side" value="239" />239
      <input type="radio" name="side" value="240" />240
      <input type="radio" name="side" value="241" />241
      <input type="radio" name="side" value="242" />242
      <input type="radio" name="side" value="243" />243
      <input type="radio" name="side" value="244" />244
      <input type="radio" name="side" value="245" />245
      <input type="radio" name="side" value="246" />246
      <input type="radio" name="side" value="247" />247
      <input type="radio" name="side" value="248" />248
      <input type="radio" name="side" value="249" />249
      <input type="radio" name="side" value="250" />250
      <input type="radio" name="side" value="251" />251
      <input type="radio" name="side" value="252" />252
      <input type="radio" name="side" value="253" />253
      <input type="radio" name="side" value="254" />254
      <input type="radio" name="side" value="255" />255
      <input type="radio" name="side" value="256" />256
      <input type="radio" name="side" value="257" />257
      <input type="radio" name="side" value="258" />258
      <input type="radio" name="side" value="259" />259
      <input type="radio" name="side" value="260" />260
      <input type="radio" name="side" value="261" />261
      <input type="radio" name="side" value="262" />262
      <input type="radio" name="side" value="263" />263
      <input type="radio" name="side" value="264" />264
      <input type="radio" name="side" value="265" />265
      <input type="radio" name="side" value="266" />266
      <input type="radio" name="side" value="267" />267
      <input type="radio" name="side" value="268" />268
      <input type="radio" name="side" value="269" />269
      <input type="radio" name="side" value="270" />270
      <input type="radio" name="side" value="271" />271
      <input type="radio" name="side" value="272" />272
      <input type="radio" name="side" value="273" />273
      <input type="radio" name="side" value="274" />274
      <input type="radio" name="side" value="275" />275
      <input type="radio" name="side" value="276" />276
      <input type="radio" name="side" value="277" />277
      <input type="radio" name="side" value="278" />278
      <input type="radio" name="side" value="279" />279
      <input type="radio" name="side" value="280" />280
      <input type="radio" name="side" value="281" />281
      <input type="radio" name="side" value="282" />282
      <input type="radio" name="side" value="283" />283
      <input type="radio" name="side" value="284" />284
      <input type="radio" name="side" value="285" />285
      <input type="radio" name="side" value="286" />286
      <input type="radio" name="side" value="287" />287
      <input type="radio" name="side" value="288" />288
      <input type="radio" name="side" value="289" />289
      <input type="radio" name="side" value="290" />290
      <input type="radio" name="side" value="291" />291
      <input type="radio" name="side" value="292" />292
      <input type="radio" name="side" value="293" />293
      <input type="radio" name="side" value="294" />294
      <input type="radio" name="side" value="295" />295
      <input type="radio" name="side" value="296" />296
      <input type="radio" name="side" value="297" />297
      <input type="radio" name="side" value="298" />298
      <input type="radio" name="side" value="299" />299
      <input type="radio" name="side" value="300" />300
      <input type="radio" name="side" value="301" />301
      <input type="radio" name="side" value="302" />302
      <input type="radio" name="side" value="303" />303
      <input type="radio" name="side" value="304" />304
      <input type="radio" name="side" value="305" />305
      <input type="radio" name="side" value="306" />306
      <input type="radio" name="side" value="307" />307
      <input type="radio" name="side" value="308" />308
      <input type="radio" name="side" value="309" />309
      <input type="radio" name="side" value="310" />310
      <input type="radio" name="side" value="311" />311
      <input type="radio" name="side" value="312" />312
      <input type="radio" name="side" value="313" />313
      <input type="radio" name="side" value="314" />314
      <input type="radio" name="side" value="315" />315
      <input type="radio" name="side" value="316" />316
      <input type="radio" name="side" value="317" />317
      <input type="radio" name="side" value="318" />318
      <input type="radio" name="side" value="319" />319
      <input type="radio" name="side" value="320" />320
      <input type="radio" name="side" value="321" />321
      <input type="radio" name="side" value="322" />322
      <input type="radio" name="side" value="323" />323
      <input type="radio" name="side" value="324" />324
      <input type="radio" name="side" value="325" />325
      <input type="radio" name="side" value="326" />326
      <input type="radio" name="side" value="327" />327
      <input type="radio" name="side" value="328" />328
      <input type="radio" name="side" value="329" />329
      <input type="radio" name="side" value="330" />330
      <input type="radio" name="side" value="331" />331
      <input type="radio" name="side" value="332" />332
      <input type="radio" name="side" value="333" />333
      <input type="radio" name="side" value="334" />334
      <input type="radio" name="side" value="335" />335
      <input type="radio" name="side" value="336" />336
      <input type="radio" name="side" value="337" />337
      <input type="radio" name="side" value="338" />338
      <input type="radio" name="side" value="339" />339
      <input type="radio" name="side" value="340" />340
      <input type="radio" name="side" value="341" />341
      <input type="radio" name="side" value="342" />342
      <input type="radio" name="side" value="343" />343
      <input type="radio" name="side" value="344" />344
      <input type="radio" name="side" value="345" />345
      <input type="radio" name="side" value="346" />346
      <input type="radio" name="side" value="347" />347
      <input type="radio" name="side" value="348" />348
      <input type="radio" name="side" value="349" />349
      <input type="radio" name="side" value="350" />350
      <input type="radio" name="side" value="351" />351
      <input type="radio" name="side" value="352" />352
      <input type="radio" name="side" value="353" />353
      <input type="radio" name="side" value="354" />354
      <input type="radio" name="side" value="355" />355
      <input type="radio" name="side" value="356" />356
      <input type="radio" name="side" value="357" />357
      <input type="radio" name="side" value="358" />358
      <input type="radio" name="side" value="359" />359
    </form>
    <button onClick="check_door()">Check</button>
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/static/js/door.js` file.

```javascript
function check_door() {
  var all_radio = document.getElementById("door_form").elements;
  var guess = null;

  for (var i = 0; i < all_radio.length; i++)
    if (all_radio[i].checked) guess = all_radio[i].value;

  rand = Math.floor(Math.random() * 360);
  if (rand == guess) window.location = "/open/";
  else window.location = "/die/";
}
```

So you can discover the `http://web.ctf.b01lers.com:1000/open/` endpoint.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
    <script src="/static/js/open_sesame.js"></script>
  </head>
  <body>
    <h1>YOU FOUND THE DOOR!</h1>
    <p>How do you open it?</p>
    <img src="/static/img/door.jpg" alt="door" style="width:60vw;" />
    <script>
      open(0);
    </script>
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/static/js/open_sesame.js` file.

```javascript
function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

function open(i) {
  sleep(1).then(() => {
    open(i + 1);
  });
  if (i == 4000000000) window.location = "/fight/";
}
```

So you can discover the `http://web.ctf.b01lers.com:1000/fight/` endpoint.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Earth</title>
    <script src="/static/js/fight.js"></script>
  </head>
  <body>
    <h1>AN ALIEN!</h1>
    <p>What do you do?</p>
    <img
      src="/static/img/alien.png"
      alt="door"
      style="width:60vw;"
    />
    </br>
    <input type="text" id="action">
    <button onClick="check_action()">Fight!</button>
  </body>
</html>
```

So you can discover the `http://web.ctf.b01lers.com:1000/static/js/fight.js` file.

```javascript
// Run to scramble original flag
//console.log(scramble(flag, action));
function scramble(flag, key) {
  for (var i = 0; i < key.length; i++) {
    let n = key.charCodeAt(i) % flag.length;
    let temp = flag[i];
    flag[i] = flag[n];
    flag[n] = temp;
  }
  return flag;
}

function check_action() {
  var action = document.getElementById("action").value;
  var flag = ["{hey", "_boy", "aaaa", "s_im", "ck!}", "_baa", "aaaa", "pctf"];

  // TODO: unscramble function
}
```

So the flag is the following.

```
pctf{hey_boys_im_baaaaaaaaaack!}
```