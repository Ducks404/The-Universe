## Internet Protocol (IP)

Packets form the foundation of data exchange over a network, which means that detection begins at the packet level. The **Internet Protocol (IP)** includes a set of standards used for routing and addressing data packets as they travel between devices on a network. IP operates as the foundation for all communications over the internet.

IP ensures that packets reach their destinations. There are two versions of IP that you will find in use today: IPv4 and IPv6. Both versions use different headers to structure packet information.

### **IPv4**

IPv4 is the most commonly used version of IP. There are thirteen fields in the header:

- **Version**: This field indicates the IP version. For an IPv4 header, IPv4 is used. 
    
- **Internet Header Length (IHL)**: This field specifies the length of the IPv4 header including any Options.
    
- **Type of Service (ToS)**: This field provides information about packet priority for delivery.
    
- **Total Length**: This field specifies the total length of the entire IP packet including the header and the data.
    
- **Identification**: Packets that are too large to send are fragmented into smaller pieces. This field specifies a unique identifier for fragments of an original IP packet so that they can be reassembled once they reach their destination.
    
- **Flags**: This field provides information about packet fragmentation including whether the original packet has been fragmented and if there are more fragments in transit.
    
- **Fragment Offset**: This field is used to identify the correct sequence of fragments.
    
- **Time to Live (TTL)**: This field limits how long a packet can be circulated in a network, preventing packets from being forwarded by routers indefinitely.
    
- **Protocol**: This field specifies the protocol used for the data portion of the packet.
    
- **Header Checksum**: This field specifies a checksum value which is used for error-checking the header.
    
- **Source Address**: This field specifies the source address of the sender.
    
- **Destination Address**: This field specifies the destination address of the receiver.
    
- **Options**: This field is optional and can be used to apply security options to a packet.
    

![An IPv4 header with its 13 fields.](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/jkb0TBrPQSq9YoCeruRfqA_e1ec815e1edd4447a9a51b7f8945ccf1_7Fe1r5PP-rO933_0njaasi_PLYxnCK70uwxT7ZVgtLukfU1L_3B4ppP4aiLOiZ1QNlZCuuLku28h-mpQ5lEnQKly8HIeoDkaEvqkdh4Xbb_U9ba52JscXUcrmQFcluGPBPqNqA1v_gYZwv_JqR4di7niNF2R5uy2JBR0r-QshhE6zOIghv4lUCWa96872A?expiry=1703808000000&hmac=LowL_2qYr4rdrmttMzhi4dvSaZu-BIlOeRDffeBTyYM)

### **IPv6**

IPv6 adoption has been increasing because of its large address space. There are eight fields in the header:

- **Version**: This field indicates the IP version. For an IPv6 header, IPv6 is used.
    
- **Traffic Class**: This field is similar to the IPv4 Type of Service field. The Traffic Class field provides information about the packet's priority or class to help with packet delivery.
    
- **Flow Label**: This field identifies the packets of a flow. A flow is the sequence of packets sent from a specific source. 
    
- **Payload Length**: This field specifies the length of the data portion of the packet.
    
- **Next Header**: This field indicates the type of header that follows the IPv6 header such as TCP.
    
- **Hop Limit**: This field is similar to the IPv4 Time to Live field. The Hop Limit limits how long a packet can travel in a network before being discarded.
    
- **Source Address**: This field specifies the source address of the sender.
    
- **Destination Address**: This field specifies the destination address of the receiver.
    

![An IPv6 header with its eight fields.](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/i8ZlXBWcQnKMc9AvaOlTrg_9ae604f634bc4ea3b0bced51911d32f1_XjvmdLkZuzfhKQ0zQ_4RnCZGNxP0FDCtB0i8iwWtu30GL05Ziixkcd3YNSK8ng5tiu3X3XVOypCPywtGP01diUAvVWEkjwGWk7E_4fpFZdntBgohToxkS5cNsyZtqKsRCmssQUmWlH8Xhn2oJKG55Kv0-CUjA8Kj3yhZXTWbjjV4pYcCH9EUwPWpyFnhCQ?expiry=1703808000000&hmac=RikyWA7NkrVnSnKgnW7rZfKc-_FTvOmEBSjHm9y9Yhs)