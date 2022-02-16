<!-- @format -->

# tcpdump

Some tcpdump questions with answer

## 1. Draw the IP Header with detailed bits

IP Header is 20 bytes

![IPv4_Packet-en svg](https://user-images.githubusercontent.com/36810834/153740999-03eb3c3a-3b8f-4bb1-96c0-42994485febc.png)

Ref:
https://en.wikipedia.org/wiki/IPv4#/media/File:IPv4_Packet-en.svg

## 2. What is tcpdump?

tcpdump is a command line tool used for analyzing network traffic

## 3. How to get the HTTPS traffic? Share the command.

We need to capture traffic on port 443 since HTTPS traffic use that port
`tcpdump port 443`

## 4. For everything on an interface, what is the command?

If interface is `eth0` then the command is
`tcpdump -i eth0`

Note: to run tcpdump root privilege is required.

## 5. Write the command to find Traffic by IP.

If IP is 10.10.10.1 then command is
`tcpdump host 10.10.10.1`

## 6. Share the filtering by Source and/or Destination?

If source or destination IP is 10.10.10.1 then
`tcpdump src 10.10.10.1`
or
`tcpdump dst 10.10.10.1`

## 7. How to find Packets by Network, write the line.

If the network is 10.10.10.1/24 then the command is
`tcpdump net 10.10.10.1/24`

## 8. Using packet contents with Hex Output, write the command.

If interace is `eth0` then the command is
`tcpdump -X -i eth0`

## 9. To find a specific port traffic, write the command.

If the port is 123 then the command is
`tcpdump port 123`

## 10. Show Traffic of One Protocol command.

If the protocol is icmp then command is
`tcpdump icmp`

## 11. Write the command showing only IP6 Traffic.

`tcpdump ip6`

## 12. Write the command for finding Traffic Using Port Ranges.

    tcpdump portrange 21-23

## 13.What are PCAP (PEE-cap) files?

- ### It’s often useful to save packet captures into a file for analysis in the future. These files are known as PCAP (PEE-cap) files, and they can be processed by hundreds of different applications, including network analyzers, intrusion detection systems, and of course by tcpdump itself. Here we’re writing to a file called capture_file using the -w switch.

  `tcpdump port 80 -w capture_file.pcap`

## 14.How are PCAP files processed and why is it so?

`tcpdump -r capture_file.pcap`

## 15.Which switch is used to write the PCAP file called capture_file?

- ### You can read PCAP files by using the -r switch. Note that you can use all the regular commands within tcpdump while reading in a file; you’re only limited by the fact that you can’t capture and process what doesn’t exist in the file already.

### Reference:

https://danielmiessler.com/study/tcpdump/

### Credit

- ### [Munshi Muzahid Hasan Tushar](https://github.com/muzahid-c/tcpdump-QA)
