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
  title: "Installations"
  url: '/blog/'
  image: widget-1-302x182.jpg
  text: 'Some text Widget1'
widget2:
  title: "Features"
  url: 'https://phlow.github.io/feeling-responsive/info/'
  text: 'Some text Widget2'
  video: '<a href="#" data-reveal-id="videoModal"><img src="/images/leakInstallation_dm.jpg" width="302" height="182" alt=""/></a>'
widget3:
  title: "Install Blinky-Lite"
  url: 'https://github.com/Phlow/feeling-responsive'
  image: widget-github-303x182.jpg
  text: 'Some text Widget'
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
callforaction:
  video: 'https://www.youtube.com/embed/ixhx7huZjTI?si=0Gq-TxCqrKp-QzCg'
  title: 'Featured Video: Blinky-Leak Installation'

permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/ixhx7huZjTI?si=0Gq-TxCqrKp-QzCg" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>

