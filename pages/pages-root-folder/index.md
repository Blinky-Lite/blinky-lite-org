---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: bridge_dm.jpg
widget1:
  title: "Install Blinky-Lite"
  url: '/docs/pages//Installation/appServerInstall.html'
  image: container302x182.jpg
  text: ''
  video: '<a href="#" data-reveal-id="videoModal"><img src="/images/container302x182YouTube.jpg" width="302" height="182" alt=""/></a>'
widget2:
  title: "Features"
  url: '/docs/pages/Overview/features.html'
  text: ''
  image: mirrotronRF302x182.jpg
widget3:
  title: "System examples"
  url: '/system-examples/'
  image: rfq_thumb.png
  text: ''

#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
#callforaction:
#  video: 'https://www.youtube.com/embed/ixhx7huZjTI?si=0Gq-TxCqrKp-QzCg'
#  title: 'Featured Video: Blinky-Leak Installation'

permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---
<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://player.vimeo.com/video/906812514?dnt=1" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>

