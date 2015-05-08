# edx-theme

[![Build Status](https://travis-ci.org/IONISx/edx-theme.svg?branch=master)](https://travis-ci.org/IONISx/edx-theme)

> Open edX responsive theme using [Bootstrap](http://getbootstrap.com/).

![Screenshot](https://raw.githubusercontent.com/IONISx/edx-theme/docs/images/responsive.png)

## Getting started

First, install `grunt-cli` and `bower` globally (or not) in order to have the required build tools.

    npm install -g grunt-cli bower

Then fetch the local depedencies.

    npm install
    bower install

Finally, run `grunt` to build the theme’s source files.
`grunt` will watch for changes and re-build the output automatically.

Run `grunt build` for a one time build.  
Run `grunt test` to lint your source files as well.

## Installation

Create /edx/app/edx_ansible/server-vars.yml

Update file permissions
```
sudo chown edx-ansible:edx-ansible /edx/app/edx_ansible/server-vars.yml
```
Re-provision:
```
sudo /edx/bin/update edx-platform release
```

## Add Zendesk Widget

To be placed at the end of `templates/theme-head-extra.html

```
<!-- Start of Cloud Genius Zendesk Widget script -->
<script>/*<![CDATA[*/window.zEmbed||function(e,t){var n,o,d,i,s,a=[],r=document.createElement("iframe");window.zEmbed=function(){a.push(arguments)},window.zE=window.zE||window.zEmbed,r.src="javascript:false",r.title="",r.role="presentation",(r.frameElement||r).style.cssText="display: none",d=document.getElementsByTagName("script"),d=d[d.length-1],d.parentNode.insertBefore(r,d),i=r.contentWindow,s=i.document;try{o=s}catch(c){n=document.domain,r.src='javascript:var d=document.open();d.domain="'+n+'";void(0);',o=s}o.open()._l=function(){var o=this.createElement("script");n&&(this.domain=n),o.id="js-iframe-async",o.src=e,this.t=+new Date,this.zendeskHost=t,this.zEQueue=a,this.body.appendChild(o)},o.write('<body onload="document._l();">'),o.close()}("//assets.zendesk.com/embeddable_framework/main.js","cloudgenius.zendesk.com");/*]]>*/</script>
<!-- End of Cloud Genius Zendesk Widget script -->
```

## Quick theme updates

```

sudo su edxapp  -s /bin/bash
cd ~
source edxapp_env
cd /edx/app/edxapp/edx-platform

cd ../themes/ionisx/
git pull
cd ../../edx-platform/
paver update_assets lms --settings=aws

paver update_assets cms --settings=aws

```

## License

[AGPL](http://en.wikipedia.org/wiki/Affero_General_Public_License)
