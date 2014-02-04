#!/usr/bin/python
import sys
import time
import fnmatch
import os
import re
import time
import re
from subprocess import call
from xml.dom.minidom import parseString

print "#################################################################################################################"
print "#                          .             .                          .             .                             #"
print "#                                                                                                               #"
print "#              .   @@@@@A   . ,@S         . A@          .     .      .             .  .A@#@@@                   #"
print "#              . @@      @G . .@r         . X@          .     @@     .             . &@      @@                 #"
print "#  :@A@. A@      @@    @A@2    @h@H@M@,   . S@          .            . ,@#@B@A@A@, .         @@    @#@#@#@2     #"
print "#  ,@. S@  &@    M#  @B  @i    @;     r@.   s@          .   @#Mh     .       :@,   .     #@#@      @G     ,@i   #"
print "#  .@  5@  M@    @@MB.   @2    @;     r@.   S@          .   ,.@#     .      @,.    .     .,  9G    @G      ;    #"
print "#   @  i@  3@    @@      @X    @:     ;@.   s@          .     @G     .    #,.      . 5@      @@    @9           #"
print "#  ,@. .i  #@    ::iihX&rr,    @&HS#iB,i    9@5A3AG&GA  .   Gi@@G5   . .@3@22rMS@. . ;h5H2G5X;r    @@           #"
print "#   h      ;2      X23S3;   .  2;AsArA    . ,Ss9592XX3  .   3ir;9i   . .M;s;GrAs#. .   s&S3S2      Sr           #"
print "#                                                                                                               #"
print "#                                                                                                               #"
print "#################################################################################################################"
print "#                                                                                                               #"
print "#                     Credits: Sudhanshu Chauhan, Nutan Kumar Panda, Shubham Mittal                             #"
print "#				                                                                                #"
print "#################################################################################################################"

class Logger(object):
    def __init__(self):
        self.terminal = sys.stdout
        self.log = open("logfile.log", "a")

    def write(self, message):
        self.terminal.write(message)
        self.log.write(message)  

sys.stdout = Logger()

count=0
b = raw_input("Enter apk filename: ")
print ""
print ""
print "Test started for "+b
call(['apktool','d',b])
flist=[]
dirp=b.strip('.apk')
rootpath="./"+dirp
ip = re.compile('((?:\d{1,3}\.){3}\d{1,3})')
email=re.compile('([\w.]+)@([\w.]+)')
simlist=["pwlist","sql","dbconnect","dbname","username","pass","passwd","pwd","user","IMEI","connecTodb","dbname","server","API", "apikey","api","ftp:"]
relist=[ip,email]
for path,name,fname in os.walk(rootpath):
 for fn in fname:
     q=path+"/"+fn
     flist.append(q)

extrm=['.xml','.smali','.yml']
for sl in simlist:
 relist.extend([re.compile(sl)])

for fl in flist:
   if any(ext in fl for ext in extrm):    
    count=0 
    for line in open(fl, "r").readlines():
      count=count+1
      for lv in relist:
        match = lv.findall(line, re.IGNORECASE)
        for mat in match: 
          print "" 
          print 'File: ',fl
          print 'String ',"'",mat,"'",'at line number',count 
          print 'Line: ',line
             
print ""
print ""
print "Manifest Permissions:"
manifile=rootpath+"/AndroidManifest.xml"
file = open(manifile,'r')
data = file.read()
file.close()
dom = parseString(data)
xmlTag = dom.getElementsByTagName('uses-permission')[0].toxml()
print xmlTag
print ""
print ""
print "-----------------------------------------------------------------------------------------------------"
print "Test Completed for "+b
print "-----------------------------------------------------------------------------------------------------"
print ""
print ""
