# Tony the Tiger

Learn how to use a Java Serialisation attack in this boot-to-root

## Task 1 : Deplot the machine

## Task 2 : Support Material

Read the material and answer the following questions.
1. What is a great IRL example of an "Object"? `Lamp`
2. What is the acronym of a possible type of attack resulting from a "serialisation" attack? `DoS`
3. What lower-level format does data within "Objects" get converted into? `byte stream`

## Task 3: Reconnaissance

We run the rustscan
```
rustscan -a 10.10.231.18 -r 1-65535 --ulimit 5000 -- -sV -T4 -oN rustscan_nmap.txt

PORT     STATE SERVICE     REASON         VERSION
22/tcp   open  ssh         syn-ack ttl 60 OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
80/tcp   open  http        syn-ack ttl 60 Apache httpd 2.4.7 ((Ubuntu))
1090/tcp open  java-rmi    syn-ack ttl 60 Java RMI
1091/tcp open  java-rmi    syn-ack ttl 60 Java RMI
1098/tcp open  java-rmi    syn-ack ttl 60 Java RMI
1099/tcp open  java-object syn-ack ttl 60 Java Object Serialization
3873/tcp open  java-object syn-ack ttl 60 Java Object Serialization
4446/tcp open  java-object syn-ack ttl 60 Java Object Serialization
4712/tcp open  msdtc       syn-ack ttl 60 Microsoft Distributed Transaction Coordinator (error)
4713/tcp open  pulseaudio? syn-ack ttl 60
5445/tcp open  smbdirect?  syn-ack ttl 60
5455/tcp open  apc-5455?   syn-ack ttl 60
5500/tcp open  hotline?    syn-ack ttl 60
5501/tcp open  tcpwrapped  syn-ack ttl 60
8009/tcp open  ajp13       syn-ack ttl 60 Apache Jserv (Protocol v1.3)
8080/tcp open  http        syn-ack ttl 60 Apache Tomcat/Coyote JSP engine 1.1
8083/tcp open  http        syn-ack ttl 60 JBoss service httpd
5 services unrecognized despite returning data. If you know the service/version, please submit the following fingerprints at https://nmap.org/cgi-bin/submit.cgi?new-service :

```
We get our first from above and when we go to website and port 8080, we found that a JBoss Application Server is running which is answer to our second question.

1. What service is running on port "8080"
`Apache Tomcat/Coyote JSP engine 1.1`

2. What is the name of the front-end application running on "8080"?
`JBoss`

## Find Tony's Flag!












   
