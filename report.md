## Part 1. ipcalc tool

1. Network address of 192.167.38.54/13:

   Network address is 192.160.0.0/13 (11000000.10100 000.00000000.00000000)

2. Conversion of the mask 255.255.255.0 to prefix and binary:

   prefix - /24

   binary - 11111111.11111111.11111111. 00000000

3. Conversion of /15 to normal and binary:

   normal - 255.254.0.0

   binary - 11111111.11111110.00000000. 00000000

4. Conversion 11111111.11111111.11111111.11110000 to normal and prefix:

   normal - 255.255.255.240

   prefix - /28

5. Minimum and maximum host in 12.167.38.4/8:

   HostMin - 12.0.0.1

   HostMax - 12.255.255.254

6. Minimum and maximum host in 12.167.38.4/11111111.11111111.00000000.00000000:

   HostMin - 12.167.0.1

   HostMax - 12.167.255.254

7. Minimum and maximum host in 12.167.38.4/255.255.254.0:

   HostMin - 12.167.38.1

   HostMax - 12.167.39.254

8. Minimum and maximum host in 12.167.38.4/4:

   HostMin - 0.0.0.1

   HostMax - 15.255.255.254

9. An application running on localhost can be accessed with the following IPs:

   194.34.23.100 - no

   127.0.0.2 - yes

   127.1.0.1 - yes

   128.0.0.1 - no

10. IPs can be used as

   10.0.0.45 - private

   134.43.0.2 - public

   192.168.4.2 - private

   172.20.250.4 - private

   172.0.2.1 - public

   192.172.0.1 - public

   172.68.0.2 - public

   172.16.255.255 - private

   10.10.10.10 - private

   192.169.168.1 - public

11. Gateway IP addresses are possible for 10.10.0.0/18:

   10.0.0.1 - no

   10.10.0.2 - yes

   10.10.10.10 - yes

   10.10.100.1 - no

   10.10.1.255 - yes

## Part 2. Static routing between two machines

1. Network interfaces ws1

   ![ws1](./screenshots/part2_1.png)

2. Network interfaces ws2

   ![ws2](./screenshots/part2_2.png)

3. The network interface corresponding to the internal network is enp0s3 on both machines

4. Set the following address and mask on ws1: 192.168.100.10/16

   ![ws1](./screenshots/part2_3.png)

5. Set the following address and mask on ws2: 172.24.116.8/12

   ![ws2](./screenshots/part2_4.png)

6. Output of the command `netplan apply` on ws1

   ![ws1](./screenshots/part2_5.png)

7. Output of the command `netplan apply` on ws2

   ![ws2](./screenshots/part2_6.png)

8. Static route from one machine to another on ws1

   ![ws1](./screenshots/part2_7.png)

9. Static route from one machine to another on ws2 

   ![ws2](./screenshots/part2_8.png)

10. Add address of ws2 to ws1

   ![ws1](./screenshots/part2_9.png)

11. Add address of ws1 to ws2

   ![ws2](./screenshots/part2_10.png)

12. Ping ws2 from ws1

   ![ws1](./screenshots/part2_11.png)

13. Ping ws1 from ws2

   ![ws2](./screenshots/part2_12.png)

14. Static route from ws1 to ws2 

   ![ws1](./screenshots/part2_13.png)

15. Static route from ws2 to ws1

   ![ws2](./screenshots/part2_14.png)

16. Ping ws2 from ws1

   ![ws1](./screenshots/part2_15.png)

17. Ping ws1 from ws2

   ![ws2](./screenshots/part2_16.png)

## Part 3. iperf3 utility

1. 8 Mbps = 0.9766 MB/s

2. 100 MB/s = 838861 Kbps

3. 1 Gbps = 1000 Mbps

4. Connection speed between ws1 and ws2 (ws1 - server, ws2 - client)

   ![ws1](./screenshots/part2_17.png)

   ![ws2](./screenshots/part2_18.png)

   Bitrate ws1 - 2.81 Gbits/sec (reciever)

   Bitrate ws2 - 2.55 Gbits/sec (sender)

5. Connection speed between ws2 and ws1 (ws2 - server, ws1 - client)

   ![ws2](./screenshots/part2_19.png)

   ![ws1](./screenshots/part2_20.png)

   Bitrate ws1 - 2.69 Gbits/sec (sender)

   Bitrate ws2 - 2.83 Gbits/sec (receiver)

## Part 4. Network firewall

1. Content of file /etc/firewall.sh on ws1

   ![ws1](./screenshots/part4_1.png)

2. Content of file /etc/firewall.sh on ws2

   ![ws2](./screenshots/part4_2.png)

3. Run the file on ws1

   ![ws1](./screenshots/part4_3.png)

4. Run the file on ws2

   ![ws2](./screenshots/part4_4.png)

5. The difference between the strategies used on ws1 and ws2 is:

   1) We can ping ws2 from ws1. Because an allow rule wasn't cancelled.

   2) We can't ping ws1 from ws2. Because, a deny rule wasn't cancelled.

   3) The first rule will be worked in both cases.

6. We can ping ws2

   ![ws1](./screenshots/part4_5.png)

7. We can't ping ws1

   ![ws2](./screenshots/part4_6.png)

8. The machine host is up

   ![ws2](./screenshots/part4_7.png)

## Part 5. Static network routing

1. The ws11 machine configuration:

   ![ws11](./screenshots/part5_1.png)

2. The ws21 machine configuration:

   ![ws21](./screenshots/part5_2.png)

3. The ws22 machine configuration:

   ![ws22](./screenshots/part5_3.png)

4. The r1 machine configuration:

   ![r1](./screenshots/part5_4.png)

5. The r2 machine configuration:

   ![r2](./screenshots/part5_5.png)

6. Restart the network service of ws11:

   ![ws11](./screenshots/part5_6.png)

7. Restart the network service of ws21:

   ![ws21](./screenshots/part5_7.png)

8. Restart the network service of ws22:

   ![ws22](./screenshots/part5_8.png)

9. Restart the network service of r1:

   ![r1](./screenshots/part5_9.png)

10. Restart the network service of r2:

   ![r2](./screenshots/part5_10.png)

11. The `ip -4 a` command on ws11:

   ![ws11](./screenshots/part5_11.png)

12. The `ip -4 a` command on ws21:

   ![ws21](./screenshots/part5_12.png)

13. The `ip -4 a` command on ws22:

   ![ws22](./screenshots/part5_13.png)

14. The `ip -4 a` command on r1:

   ![r1](./screenshots/part5_14.png)

15. The `ip -4 a` command on r2:

   ![r2](./screenshots/part5_15.png)

16. Ping ws22 from ws21

   ![ws21](./screenshots/part5_16.png)

17. Ping r1 from ws11

   ![ws11](./screenshots/part5_17.png)

18. Enable IP forwarding on r1

   ![r1](./screenshots/part5_18.png)

19. Enable IP forwarding on r2

   ![r2](./screenshots/part5_19.png)

20. Changed `/etc/sysctl.conf` file on r1:

   ![r1](./screenshots/part5_20.png)

21. Changed `/etc/sysctl.conf` file on r2:

   ![r2](./screenshots/part5_21.png)

22. I added the default route (gateway) earlier, so you can see screenshots at the beginning of Part 5

23. Output of `ip r` command on ws11:

   ![ws11](./screenshots/part5_22.png)

24. Output of `ip r` command on ws21:

   ![ws21](./screenshots/part5_23.png)

25. Output of `ip r` command on ws22:

   ![ws22](./screenshots/part5_24.png)

26. Ping r2 from ws11

   ![ws11](./screenshots/part5_27.png)

27. Output of the `sudo tcpdump -tn -i enp0s3` command

   ![r2](./screenshots/part5_28.png)

28. I added static routes to r1 and r2 configuration files earlier. You can see screenshots above.

29. Output of command `ip r` on r1

   ![r1](screenshots/part5_25.png)

30. Output of command `ip r` on r2

   ![r2](./screenshots/part5_26.png)

31. Output of command `ip r list 10.10.0.0/18` 

   ![ws11](./screenshots/part5_29.png)

32. Output of command `ip r list 0.0.0.0/0`

   ![ws11](./screenshots/part5_30.png)

33. In the case with the address 0.0.0.0/0 output of command is the address of this machine (ws11). Because this

   address will be works in any cases even if the network wouldn't work. In case with the address 10.10.0.0/18 we have

   define gateway, which address we can see in the output. 

34. Output of `traceroute 10.0.20.10` command

   ![ws11](./screenshots/part5_31.png)

35. Output of `tcpdump -tnv -i enp0s3` command

   ![r1](./screenshots/part5_32.png)

36. Traceroute send series of packages to specified address. Every time increase TTL (time of package life) for 1. TTL

   usually is a number of gateways on the path between the machine and specified address.

37. Ping a non-existent IP from ws 11

   ![ws11](./screenshots/part5_33.png)

38. Traffic capture on r1 going through enp0s3

   ![r1](./screenshots/part5_34.png)

## Part 6. Dynamic IP configuration using DHCP

1. Changed file `/etc/dhcp/dhcpd.conf` on r2

   ![r2](./screenshots/part6_1.png)

2. Changed file `/etc/resolv.conf` on r2

   ![r2](./screenshots/part6_2.png)

3. Restart the DHCP service on r2

   ![r2](./screenshots/PART6_3.png)

4. The output of `ip a` command on ws21

   ![ws21](./screenshots/part6_4.png)

5. Ping ws22 from ws21

   ![ws21](./screenshots/part6_9.png)

6. Changed `/etc/netplan/00-installer-config.yaml` file on ws11

   ![ws11](./screenshots/part6_5.png)

7. Changed `/etc/dhcp/dhcpd.conf` file on r1

   ![r1](./screenshots/part6_6.png)

8. Changed `/etc/resolf.conf` file on r1

   ![r1](./screenshots/part6_7.png)

9. The output of the command `systemctl restart isc-dhcp-server`

   ![r1](./screenshots/part6_8.png)

10. The output of the command `ip a` on ws11

   ![ws11](./screenshots/part6_10.png)

11. Ping ws22 from ws11

   ![ws22](./screenshots/part6_11.png)

12. IP on ws21 before changes

   ![ws21](./screenshots/part6_12.png)

13. IP on ws21 after changes

   ![ws21](./screenshots/part6_13.png)

14. To get new IP address I use command `dhclient` and `dhclient -r`. We release the old IP address using flag `-r` and

   asking the new IP address with command `dhclient`.

## Part 7. NAT

1. Changed file `/etc/apache2/ports.conf` on ws22

   ![ws22](./screenshots/part7_1.png)

2. Changed file `/etc/apache2/ports.conf` on r1

   ![r1](./screenshots/part7_2.png)

3. Start the Apache web server on ws22

   ![ws22](./screenshots/part7_3.png)

4. Start the Apache web server on r1

   ![r1](./screenshots/part7_4.png)

5. Ping r1 from ws22 after creating firewall.sh

   ![ws22](./screenshots/part7_5.png)

6. Ping r1 from ws22 after changing firewall.sh

   ![ws22](./screenshots/part7_6.png)

7. File containing our firewall settings on r2

   ![r2](./screenshots/part7_7.png)

8. Check the TCP connection from ws22 to r1

   ![ws22](./screenshots/part7_8.png)

9. Check the TCP connection from r1 to ws22

   ![r1](./screenshots/part7_9.png)
