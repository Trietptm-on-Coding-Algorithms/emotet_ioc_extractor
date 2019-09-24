# emotet_ioc_extractor

A script to extract c2 and rsa key from dump files via Winappdbg.

# Requirements
A test machine -
VMware install Win7(x86)

pefile -
https://github.com/erocarrera/pefile

winappdbg -
https://github.com/MarioVilas/winappdbg

# IOC
https://github.com/seth1002/emotet_ioc_extractor/tree/master/samples

# Sample
python ./extract_c2.py 986a219e61c646ba1c40344adab6c65b95bb0258

('start', ['C:\\Users\\seth1002\\Desktop\\ddd.exe'])
hit break
caller addr:00531574
hit sig at:
005343A1: 68 00 80 00 00 6a 6a 68  h....jjh

Hit shell code block!
00533000        00010000
dump shell code!
dump final payload!

-----------------------------
extract ioc from:pe.dump

c2 list:
190.79.251.99:21
189.245.216.217:143
189.189.214.1:21
62.75.171.248:7080
133.130.73.156:8080
203.150.19.63:443
216.154.222.52:7080
149.202.153.251:8080
5.189.148.98:8080
83.110.75.153:8090
95.178.241.254:465
190.55.39.215:80
70.45.30.28:80
181.230.126.152:8090
83.169.33.157:8080
190.55.86.138:8443
201.113.23.175:443
113.52.135.33:7080
139.59.242.76:8080
190.171.105.158:7080
176.58.93.123:80
190.13.146.47:443
143.95.101.72:8080
138.197.140.163:8080
190.10.194.42:8080
190.92.103.7:80
78.109.34.178:443
45.33.1.161:8080
108.179.216.46:8080
152.168.220.188:80
159.69.211.211:7080
94.177.253.126:80
93.78.205.196:443
190.146.81.138:8090
46.32.229.152:8080
181.113.229.139:990
178.249.187.150:7080
216.70.88.55:8080
200.82.147.93:7080

rsa key:
30 68 02 61 00 ce 36 ea e3 75 d6 7d 8b 64 39 3f 26 24 bd dd 62 16 1b b7 c6 09 09
 8f e2 1e 72 20 95 31 27 0a e3 c2 d1 95 7b 10 9e 94 3d 96 2a b0 f0 f6 c6 bf c4 a
c 26 40 a9 37 6f 67 d4 87 09 c7 5e 3a 12 a5 1e e9 2d a0 e8 ee 91 1c 88 90 79 cb
a8 63 6c fc ab 49 f2 f7 17 1b bb e0 cd 92 01 2d 00 ae 3d ee 01 02 03 01 00 01
kernel32!CreateProcessW called from 00531574 by thread 468 at process 2212