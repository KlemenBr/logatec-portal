# LOG-a-TEC portal

This repository contains content for the LOG-a-TEC portal.

Content for pages is written in Markdown in files under `content/pages`.

Add any images to be included in pages to `content/img`. Images in editable
form are in `src` (editable format is not uploaded to the server).

Static CSS and Javascript files are under `theme/static`. HTML templates are in
`theme/templates`. Edit the templates if you want to change the header or other
parts of the portal that are common across all pages.

## Uploading content to the server

HTML is generated by [Pelican](http://getpelican.com). Pelican generates static
HTML pages that are then uploaded to the server.

### Setup

You need Python, PIP and Virtualenv installed. These are usually already
installed. If not install them now:

    $ sudo apt-get install python-virtualenv python-pip

Now clone the repository:

    $ git clone git@github.com:sensorlab/logatec-portal.git

### Generate HTML

    $ cd logatec-portal
    $ make

You can now check the generated website by opening `output/index.html` in a
browser.

### Upload to server

Before uploading to the server, please make sure that your changes are merged
into [sensorlab/logatec-portal](https://github.com/sensorlab/logatec-portal)!

You need to have a user account on `log-a-tec.eu` and your user needs to be the
member of the `logatec-web` group.

    $ rsync -avz output/ log-a-tec.eu:/home/administrator/web/logatec
