### Common flow

`tcpdump -D`
-
- D : Displays available interfaces

`tcpdump -i eth0 -v -c5`
-
- i : interface
- v : view detailed data
- c5: capture 5 packets

`tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &`
-
- nn: Don't resolve IP names
- port: filters for port
- w : file to output data to
- & : run in background

`tcpdump -nn -r capture.pcap -v`
-
- r : read from given file
