============================
repository: get_usbr_webdata
============================
get_usbr_webdata v1.4.0
12 December 2016
POC: Gunnar Leffler

USAGE:
get_usbr_webdata {daily|realtime} <lookback window> <stationlist>

EXAMPLES:
get last 2 days hours of realtime data:
  get_usbr_webdata realtime 24h stations.realtime.list
  get_usbr_webdata realtime 2   stations.list

get last weeks worth of daily data:
  get_usbr_webdata daily 1w stations.daily.list
  get_usbr_webdata daily 7  stations.list

This program get data from the USBR's web service and converts it to SHEF for
transfer/ingestion into another database. It uses alias files to convert the
physical element codes the USBR uses to PE codes found in the SHEF manual.

DEPENDENCIES:
 Python 2.7.12
  Requests 2.11+ 
 This program expects the following alias files to be in the current working directory (PWD):
  daily.alias
  realtime.alias

------
FILES:
------

get_usbr_webdata.py
-------------------
Data acquisition script.

daily.alias
-----------
This file is required by script, it maps the PE codes the USBR daily database uses to PE codes found in the SHEF manual.

realtime.alias
--------------
This file is required by script, it maps the PE codes the USBR daily database uses to PE codes found in the SHEF manual.

daily.doc
---------
Word document from the USBR that explains their "daily webservice."

instant.doc
-----------
Word document from the USBR that explains their "instantaneous webservice."

get_daily.sh
------------
example script that gets daily data from USBR webservice.

get_realtime.sh
---------------
example script that gets realtime data from USBR webservice.

filterA
-------
Program that filters SHEF .A messages to only post new data.

README.txt
----------
This readme file.
