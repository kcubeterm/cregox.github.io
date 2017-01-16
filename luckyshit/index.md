---
permalink: /luckyshit/
layout: page
title: luckyshit
published: true
---

This is a game I've programmed in my first Hackathon, along with 3 great folks I've met there, at [IME USP 2014 Sep 14](https://www.hackerleague.org/hackathons/hackathon-usp-slash-ime). That was just 1 day before my second and last play presentation, "[Não esqueça de abaixar a tampa](http://abaixatampa.com/)" (something like "Don't forget to put the toilet sit down"). Busy weekend. [The source code can be found at GitHub](https://github.com/monnacs/luckyshit).

<script type='text/javascript' src='https://ssl-webplayer.unity3d.com/download_webplayer-3.x/3.0/uo/jquery.min.js'></script>
<script type="text/javascript">
<!--
var unityObjectUrl = "http://webplayer.unity3d.com/download_webplayer-3.x/3.0/uo/UnityObject2.js";
if (document.location.protocol == 'https:')
  unityObjectUrl = unityObjectUrl.replace("http://", "https://ssl-");
document.write('<script type="text\/javascript" src="' + unityObjectUrl + '"><\/script>');
-->
</script>
<script type="text/javascript">
<!--
  var config = {
    width: 960,
    height: 600,
    params: { enableDebugging:"0" }

  };
  var u = new UnityObject2(config);

  jQuery(function() {

    var $missingScreen = jQuery("#unityPlayer").find(".missing");
    var $brokenScreen = jQuery("#unityPlayer").find(".broken");
    $missingScreen.hide();
    $brokenScreen.hide();

    u.observeProgress(function (progress) {
      switch(progress.pluginStatus) {
        case "broken":
          $brokenScreen.find("a").click(function (e) {
            e.stopPropagation();
            e.preventDefault();
            u.installPlugin();
            return false;
          });
          $brokenScreen.show();
        break;
        case "missing":
          $missingScreen.find("a").click(function (e) {
            e.stopPropagation();
            e.preventDefault();
            u.installPlugin();
            return false;
          });
          $missingScreen.show();
        break;
        case "installed":
          $missingScreen.remove();
        break;
        case "first":
        break;
      }
    });
    u.initPlugin(jQuery("#unityPlayer")[0], "https://dl.dropboxusercontent.com/u/140249/luckyshit/luckyshit.unity3d");
  });
-->
</script>
<style type="text/css">
<!--
body {
  font-family: Helvetica, Verdana, Arial, sans-serif;
  background-color: white;
  color: black;
  text-align: center;
}
p.header {
  font-size: small;
}
p.header span {
  font-weight: bold;
}
p.footer {
  font-size: x-small;
}
div.content {
  margin: auto;
  width: 960px;
}
div.broken,
div.missing {
  margin: auto;
  position: relative;
  top: 50%;
  width: 193px;
}
div.broken a,
div.missing a {
  height: 63px;
  position: relative;
  top: -31px;
}
div.broken img,
div.missing img {
  border-width: 0px;
}
div.broken {
  display: none;
}
div#unityPlayer {
  cursor: default;
  height: 600px;
  width: 960px;
}
-->
</style>
<div class="content">
  <div id="unityPlayer">
    <div class="missing">
      <a href="http://unity3d.com/webplayer/" title="Unity Web Player. Install now!">
        <img alt="Unity Web Player. Install now!" src="http://webplayer.unity3d.com/installation/getunity.png" width="193" height="63" />
      </a>
    </div>
    <div class="broken">
      <a href="http://unity3d.com/webplayer/" title="Unity Web Player. Install now! Restart your browser after install.">
        <img alt="Unity Web Player. Install now! Restart your browser after install." src="http://webplayer.unity3d.com/installation/getunityrestart.png" width="193" height="63" />
      </a>
    </div>
  </div>
</div>