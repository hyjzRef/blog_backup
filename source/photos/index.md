---
layout: post
slug: "photos"
title: "相册"
noDate: "true"
comments: "false"
---
<link rel="stylesheet" href="./ins.css">
<div class="photos-btn-wrap">
<p class="photos-btn active" href="javascript:void(0)">相册</p>
</div>
<div class="instagram itemscope">
<a href="https://www.instagram.com/litten225/" target="_blank" class="open-ins">图片正在加载中…</a>
</div>
<script>
  (function() {
    var loadScript = function(path) {
      var $script = document.createElement('script')
      document.getElementsByTagName('body')[0].appendChild($script)
      $script.setAttribute('src', path)
    }
    setTimeout(function() {
      loadScript('./ins.js')
    }, 0)
  })()
</script>