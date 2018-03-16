+++
# Hero widget.
widget = "hero"
active = true
date = 2018-03-12

title = "Research and conservation for Apes"

# Order that this section will appear in.
weight = 3

# Overlay a color or image (optional).
#   Deactivate an option by commenting out the line, prefixing it with `#`.
[header]
  overlay_color = "#666"  # An HTML color value.
  overlay_img = "headers/femGib.jpg"  # Image path relative to your `static/img/` folder.
  overlay_filter = 0.1 # Darken the image. Value in range 0-1.

# Call to action button (optional).
#   Activate the button by specifying a URL and button label below.
#   Deactivate by commenting out parameters, prefixing lines with `#`.
# [cta]
#  url = "./post/getting-started/"
#  label = '<i class="fa fa-download"></i> Install Now'
+++

I study behavioral ecology and work on gibbon conservation since 2008, including social network research, population survey and monitoring, and biodiversity conservation project :rocket:
<br>
<small><a id="academic-release" href="https://sourcethemes.com/academic/updates">Latest release</a></small>
<br><br>

<script type="text/javascript">
  (function defer() {
    if (window.jQuery) {
      jQuery(document).ready(function(){
        GetLatestReleaseInfo();
      });
    } else {
      setTimeout(function() { defer() }, 50);
    }
  })();  
  function GetLatestReleaseInfo() {
    $.getJSON('https://api.github.com/repos/gcushen/hugo-academic/tags').done(function (json) {
      let release = json[0];
      // let downloadURL = release.zipball_url;
      $('#academic-release').text('I use academic theme Latest release ' + release.name);  
    });    
}  
</script>
