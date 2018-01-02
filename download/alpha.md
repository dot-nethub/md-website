---
layout: base
title: Alpha Download
navgroup: download
---
<div class="row">
  <div class="small-12 columns">
    <h1>Download</h1>

    <h5>The alpha MonoDevelop release is: <strong>{{ site.data.alpharelease.version }}</strong></h5>
    <p>Please choose your operating system to view the available packages. Source code is available on <a href="https://github.com/mono/monodevelop">GitHub</a> (viewing only) or as a <a href="https://download.mono-project.com/sources/monodevelop/">Tarball</a>.</p>

    <dl id="mono-download" class="tabs horizontal" data-tab data-options="deep_linking: true; scroll_to_content: false">
      <dd class="active"><a href="#download-mac"><i class="fa fa-apple"></i>&nbsp;Mac OS X</a></dd>
      <dd><a href="#download-lin"><i class="fa fa-linux"></i>&nbsp;Linux</a></dd>
      <dd><a href="#download-win"><i class="fa fa-windows"></i>&nbsp;Windows</a></dd>
    </dl>

    <div class="tabs-content" id="mono-download-panel">
      <div class="panel content active" id="download-mac" style="padding: 20px 10px 10px 10px">
        <h3>Visual Studio for Mac is available as a Mac Disk Image (.dmg)</h3>
        <div>
          <a href="{{ site.data.alpharelease.monodevelop_mac_url }}" class="button radius"><i class="fa fa-download"></i> Download Visual Studio for Mac</a>
          <p>Supported on Mac OS X 10.11 and later.</p>
        </div>
      </div>
      <div class="panel content active" id="download-lin" style="padding: 10px 10px 10px 10px">
        <h3>MonoDevelop for Linux is available as a Flatpak package (.flatpakref)</h3>
        <div>
          <a href="{{ site.data.alpharelease.monodevelop_linux_url }}" class="button radius"><i class="fa fa-download"></i> Download MonoDevelop</a>
          <p>Supported on any distribution with <a href="https://flatpak.org">Flatpak</a> 0.8.3+</p>
          <hr />
          <p>Currently this download only works on x86-64 operating systems. We plan to offer x86 and ARM64 builds in the future.</p>
        </div>
      </div>
      <div class="panel content" id="download-win" style="padding: 20px 10px 10px 10px">
        <h3>MonoDevelop for Windows is available from source only</h3>
        <p>Please refer to the <a href="/developers/building-monodevelop">building guide</a> for more information about how to install and configure your MonoDevelop.</p>
        <hr />
        <h5>GTK# for .NET</h5>
        <p>Installer for running Gtk#-based applications on Microsoft .NET:</p>
        <div>
          <a href="http://www.mono-project.com/download/#download-win" class="button radius small"><i class="fa fa-download"></i> Download Gtk#</a>
        </div>
      </div>
    </div>

    <h2>Release Notes</h2>
    <p>Check out the release notes of all MonoDevelop versions <a href="/documentation/release-notes/">here</a>.</p>

    <h2>Alpha and Beta updates</h2>
    <p>To try pre-release packages, check the <a href="/download/alpha/">alpha</a> or <a href="/download/beta/">beta</a> download pages.</p>
  </div>
</div>

<script>
function runScripts() {
  $(document).ready(function() {
    function activate(os,distro) {
      $('#mono-download>dd.active').removeClass();
      $('#mono-download>dd:has(a[href=#download-' + os + '])').addClass('active');
      $('#mono-download-panel>div.panel.active').removeClass('active');
      $('#mono-download-panel>#download-' + os).addClass('active');
    }
    if (window.location.hash) {
      if (window.location.hash.search("download-lin-") >= 0) {
        activate('lin');
      }
    }
    else {
      if (window.navigator.appVersion.search('Linux') >= 0 || window.navigator.platform.search('Linux') >= 0) {
        activate('lin');
      } else if (window.navigator.appVersion.search('Windows') >= 0 || window.navigator.platform.search('Windows') >= 0) {
        activate('win');
      }
    }
  });
}
</script>