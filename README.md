 
 ​<!DOCTYPE html​> 
 ​<​html​> 
 ​<​head​> 
 ​  ​<!-- 
 ​    If you are serving your web app in a path other than the root, change the 
 ​    href value below to reflect the base path you are serving from. 
  
 ​    The path provided below has to start and end with a slash "/" in order for 
 ​    it to work correctly. 
  
 ​    For more details: 
 ​    * https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base 
 ​  --> 
 ​  ​<​base​ ​href​="​/​"​> 
  
 ​  ​<​meta​ ​charset​="​UTF-8​"​> 
 ​  ​<​meta​ ​content​="​IE=Edge​" ​http-equiv​="​X-UA-Compatible​"​> 
 ​  ​<​meta​ ​name​="​description​" ​content​="​A resource to help developers evaluate and use Flutter.​"​> 
  
 ​  ​<!-- iOS meta tags & icons --> 
 ​  ​<​meta​ ​name​="​apple-mobile-web-app-capable​" ​content​="​yes​"​> 
 ​  ​<​meta​ ​name​="​apple-mobile-web-app-status-bar-style​" ​content​="​black​"​> 
 ​  ​<​meta​ ​name​="​apple-mobile-web-app-title​" ​content​="​gallery​"​> 
 ​  ​<​link​ ​rel​="​apple-touch-icon​" ​href​="​icons/Icon-192.png​"​> 
  
 ​  ​<!-- Favicon --> 
 ​  ​<​link​ ​rel​="​icon​" ​type​="​image/png​" ​href​="​favicon.png​" ​sizes​="​32x32​"/> 
  
 ​  ​<​title​>​Flutter Gallery​</​title​> 
 ​  ​<​style​> 
 ​  ​body​ { 
 ​    ​background-color​:​ ​#​030303​; 
 ​  } 
 ​  ​</​style​> 
 ​  ​<​link​ ​rel​="​manifest​" ​href​="​manifest.json​"​> 
 ​  ​<​script​> 
 ​    ​let​ ​searchParams​ ​=​ ​new​ ​URLSearchParams​(​window​.​location​.​search​)​; 
 ​    ​if​ ​(​searchParams​.​has​(​'renderer'​)​)​ ​{ 
 ​      ​window​.​flutterWebRenderer​ ​=​ ​searchParams​.​get​(​'renderer'​)​; 
 ​      ​console​.​log​(​searchParams​.​get​(​'renderer'​)​ ​+​ ​' renderer requested in the URL'​)​; 
 ​    ​} 
  
 ​    ​// The value below is injected by flutter build, do not touch. 
 ​    ​var​ ​serviceWorkerVersion​ ​=​ ​null​; 
 ​  ​</​script​> 
 ​  ​<​script​ ​src​="​flutter.js​" ​defer​>​</​script​> 
 ​</​head​> 
 ​<​body​> 
  
 ​  ​<​div​ ​id​="​loading​"​> 
 ​    ​<​style​> 
 ​      ​body​ { 
 ​        ​inset​:​ ​0​; ​overflow​:​ hidden; 
 ​        ​margin​:​ ​0​; ​padding​:​ ​0​; 
 ​        ​position​:​ fixed; 
 ​      } 
 ​      ​#​loading​ { 
 ​        ​align-items​:​ center; 
 ​        ​display​:​ flex; 
 ​        ​height​:​ ​100​%​; 
 ​        ​justify-content​:​ center; 
 ​        ​width​:​ ​100​%​; 
 ​      } 
 ​      ​#​loading​ ​img​ { 
 ​        ​animation​:​ ​1​s​ ease-in-out ​0​s​ infinite alternate breathe; 
 ​        ​opacity​:​ ​.66​; 
 ​        ​transition​:​ opacity ​.4​s​; 
 ​      } 
 ​      ​#​loading​.​main_done​ ​img​ { 
 ​        ​opacity​:​ ​1​; 
 ​      } 
 ​      ​#​loading​.​init_done​ ​img​ { 
 ​        ​animation​:​ ​.33​s​ ease-in-out ​0​s​ ​1​ forwards zooooom; 
 ​        ​opacity​:​ ​.05​; 
 ​      } 
 ​      ​@keyframes​ breathe { ​from​ { ​transform​:​ ​scale​(​1​) } ​to​ { ​transform​:​ ​scale​(​0.95​)}} 
 ​      ​@keyframes​ zooooom { ​from​ { ​transform​:​ ​scale​(​1​) } ​to​ { ​transform​:​ ​scale​(​10​)}} 
 ​      ​</​style​> 
 ​    ​<​img​ ​src​="​icons/Icon-192.png​" ​alt​="​Loading indicator...​" /> 
 ​  ​</​div​> 
  
 ​  ​<​script​> 
 ​    ​window​.​addEventListener​(​'load'​,​ ​function​(​)​ ​{ 
 ​      ​var​ ​loading​ ​=​ ​document​.​querySelector​(​'#loading'​)​; 
 ​      ​_flutter​.​loader​.​loadEntrypoint​(​{ 
 ​        ​serviceWorker​: ​{ 
 ​          ​serviceWorkerVersion​: ​serviceWorkerVersion​, 
 ​        ​} 
 ​      ​}​)​.​then​(​function​(​engineInitializer​)​ ​{ 
 ​        ​loading​.​classList​.​add​(​'main_done'​)​; 
 ​        ​return​ ​engineInitializer​.​initializeEngine​(​)​; 
 ​      ​}​)​.​then​(​function​(​appRunner​)​ ​{ 
 ​        ​loading​.​classList​.​add​(​'init_done'​)​; 
 ​        ​return​ ​appRunner​.​runApp​(​)​; 
 ​      ​}​)​.​then​(​function​(​app​)​ ​{ 
 ​        ​// Wait a few milliseconds so users can see the "zoooom" animation 
 ​        ​// before getting rid of the "loading" div. 
 ​        ​window​.​setTimeout​(​function​(​)​ ​{ 
 ​          ​loading​.​remove​(​)​; 
 ​        ​}​,​ ​200​)​; 
 ​      ​}​)​; 
 ​    ​}​)​; 
 ​  ​</​script​> 
  
 ​</​body​> 
 ​</​html​>
