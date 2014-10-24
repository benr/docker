==Building==

''
docker build --tag="benr/cuddledns:0.2" .
''


==Running==

''
docker run -d -p 53:53 -p 53:53/udp benr/cuddledns:0.2
''
