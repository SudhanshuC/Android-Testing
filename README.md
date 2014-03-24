Android-Testing
===============

Moblizer helps you do static analysis of any android application or .apk file. As it is a very premature tool we have included very limited functionality such as information disclosure automation from the source code of the .apk file. And there are certain limitations but still we are useing it in our daily pentesting projects and it helped us saving lots of time and decreases our effort. Hope it will help you also.


Pre-Requiusites:
----------------
1. apk tool installed in your system.
2. python 2.x installed.


How to use Moblizer:
--------------------
1. Copy moblizer.py to the apk tool directory.
2. Copy your .apk file to the same path.
3. Run moblizer.py using commandline. Then it will ask you to provide your apk file name.
4. Just provide your apk file name.
5. It will fetch all the codes which contains any sensitive keyword such as email, ip, username etc and put it in logfile.log where you can analyze all those.
6. It also provides you Manifest permission details in the logfile itself.
