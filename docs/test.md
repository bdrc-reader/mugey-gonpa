## test 2

<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Demo Viewer</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body style="margin:0px">
    <iframe
      style="position:fixed;width:100%;height:100%;border:none;"
      src="http://library.bdrc.io/scripts/embed-iframe.html?work=bdr:W22084&origin=website.com">
    </iframe>
  </body>
</html>

## test 1

<div id="viewer" class="demo"></div>
<script src="http://library.bdrc.io/scripts/src/lib/mirador/mirador.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@dbmdz/mirador-keyboardnavigation@1.1.0/keyboardNavigation.min.js"></script>      
<script src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/requirejs@2.3.6/require.js"></script>
<script src="https://cdn.jsdelivr.net/npm/jsewts@1.0.2/src/jsewts.min.js"></script>
<script type="module" src="http://library.bdrc.io/scripts/src/lib/transliterators.js"></script>
<script type="module" src="http://library.bdrc.io/scripts/src/lib/miradorSetup.js"></script>
<script type="module">
  let miradorConfig, miradorSetUI
  async function init() {
     const urlParams = new URLSearchParams(window.location.search);
     const work = urlParams.get('work');
     let data = [
        { "collectionUri" : "http://presentation.bdrc.io/2.1.1/collection/wio:"+work, location:"" }
     ]
     let config = miradorConfig(data);
     window.Mirador( config )
     miradorSetUI();
  }
  let waiter = setInterval( async ()=>{        
     if(_ && window.moduleLoaded &&  window.moduleLoaded.JsEWTS && window.moduleLoaded.Sanscript && window.moduleLoaded.pinyin4js) { {
        clearInterval(waiter);
        miradorConfig = window.miradorConfig
        miradorSetUI  = window.miradorSetUI
        init();
     }
  },100)
</script>
