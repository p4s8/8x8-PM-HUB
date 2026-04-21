<!DOCTYPE html>
<html>
<head><style>body{margin:0;overflow:hidden;}</style></head>
<body>
<div id="__8x8-chat-button-container-script_57167975869e1fde95838f4.46210593"></div>
<script type="text/javascript">
(function(c,f,ef){
    var typeofC=Object.prototype.toString.call(c);
    var props=(typeofC==='[object Object]'&&c)||{};
    var cb=f||(typeofC==='[object Function]'&&c);
    var config={
        scriptUuid:"script_57167975869e1fde95838f4.46210593",
        tenant:"bmljaG9sYXNkZXBsb3ltZW50MDE",
        channelName:"DO NOT TOUCH - PM HUB",
        channelUuid:"jWNqnrNiQnOHEt9mv2ow0w",
        domain:"https://vcc-eu5.8x8.com",
        buttonContainerId:"__8x8-chat-button-container-script_57167975869e1fde95838f4.46210593",
        align:"right"
    };
    var url=new URL("https://cloud8-cc-geo.8x8.com/vcc-chat-channels/public/webchat/discovery");
    var params={domain:config.domain,tenant:config.tenant,channelUuid:config.channelUuid};
    url.search=new URLSearchParams(params).toString();
    fetch(url)
        .then(function(r){return r.json();})
        .then(function(data){config.domain=!data.domain?config.domain:data.domain;})
        .catch(function(e){console.warn('Discovery failed',e);})
        .finally(function(){loadChat();});
    function loadChat(){
        var se=document.createElement("script");
        se.type="text/javascript";se.async=true;
        se.src=props.loaderURL||(config.domain+"/CHAT/common/js/chatv3.js");
        Object.keys(config).forEach(function(k){se.dataset[k]=config[k];});
        Object.keys(props).forEach(function(k){se.dataset[k]=props[k];});
        function handleInitEvent(e){
            e.detail.init(config,cb);
            se.removeEventListener('init',handleInitEvent);
            // Wait for button to render, click it, then hide it
            var tries=0;
            var poll=setInterval(function(){
                // Find any clickable element in the button container
                var container=document.getElementById('__8x8-chat-button-container-script_57167975869e1fde95838f4.46210593');
                var btn=container&&container.querySelector('*[onclick],button,a,div[role="button"],img');
                if(!btn&&container) btn=container.querySelector('*');
                if(btn){
                    btn.click();
                    // Hide the button after clicking
                    if(container) container.style.display='none';
                    clearInterval(poll);
                } else if(++tries>100){clearInterval(poll);}
            },150);
        }
        se.addEventListener('init',handleInitEvent);
        se.addEventListener('customerror',function(e){ef&&ef(e);});
        var os=document.getElementsByTagName("script")[0];
        os.parentNode.insertBefore(se,os);
    }
})();
</script>
</body>
</html>
