webNUT
======

A simple web interface for NUT ([Network UPS Tools][1])
servers, built on Pyramid, Bootstrap, and
[python-nut2][2].

[1]: http://www.networkupstools.org/ "Network UPS Tools"
[2]: https://github.com/george2/python-nut2 "python-nut2"

## Setup

Rename `webnut/config.example.py` to `webnut/config.py` and set the
variables in that file to reflect your NUT server configuration. Then
serve webNUT as you would any Pyramid app, using `pserve` or through
your production-ready server of choice.

Notes for myself (github.com/howardtopher):
```
cd /opt/webNUT/
python3 -m venv /opt/webNUT/
bin/pip install --upgrade pip setuptools
bin/pip install -e .
bin/pserve development.ini OR bin/pserve production.ini 
```

Rename `webnut/config.example.py` to `webnut/config.py`
Adjust username, password in webnut/config.py

Start up script created at: /etc/systemd/system/webnut.service

Web pages expect for locally hosted JS and CSS libraries in /assets directory.


## Screenshots

The index lists available UPS devices, along with their description,
status, and battery charge:

![Index](screenshots/ups_index.png "Index")

Clicking on a UPS's name takes you to a details view that shows a quick
status indicator, as well as the values of all variables set on the
device:

![UPS View](screenshots/ups_view.png "UPS View")
