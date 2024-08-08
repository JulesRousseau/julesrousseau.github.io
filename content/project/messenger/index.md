---
title: Secured Messenger (Java)
date: 2024-02-01
external_link:
tags:
  - Messenger
  - Signal
  - Java
---

<p style="text-align: right">
  <span style="font-size: 2em;">{{< icon name="hero/user-group" >}}</span>
  <span style="font-size: 2em; margin-left: 10px">{{< icon name="devicon/java" >}}</span>
</p>


This project is a console application implementing a secure messenger based on the [Signal app algorithm](https://signal.org/docs/specifications/doubleratchet/doubleratchet.pdf). The aim was to program end-to-end encryption through sockets for both the server and clients. Each client connects to the server, generates its certificate, and sends it to the server for storage. The clients use the Double Ratchet algorithm to generate root keys, encrypt their messages with AES-GCM, and use the Diffie-Hellman protocol to exchange keys, ensuring that only the clients share the secret key to decrypt the messages. The server acts solely as an intermediary and stores the certificates. Each client is managed by a client handler.

Here is an example of a client interface. The command line is written after the Messenger.Server is running.

<pre style="font-size: 0.7em; line-height: 1.2;"> > java Messenger.Client

Logging to Messenger ...

<font color="#2AA1B3">  ___  ___                                           </font><font color="#26A269">| Version : 1.0.0</font>
<font color="#2AA1B3"> |   \/   |                                          </font><font color="#26A269">| Coding : Java</font>
<font color="#2AA1B3"> |  \  /  | ___  ___ ___  ___ _ __   __ _  ___ _ __  </font><font color="#26A269">| Creators : DEPARTOUT-Pignard Gabriel</font>
<font color="#2AA1B3"> |  |\/|  |/ _ \/ __/ __|/ _ \ &apos;_ \ / _` |/ _ \ &apos;__| </font><font color="#26A269">|            LOEZIC Antonin</font>
<font color="#2AA1B3"> |  |  |  |  __/\__ \__ \  __/ | | | (_| |  __/ |    </font><font color="#26A269">|            ROUSSEAU Jules</font>
<font color="#2AA1B3"> |__|  |__|\___||___/___/\___|_| |_|\__, |\___|_|    </font><font color="#26A269">| </font>
<font color="#2AA1B3">                                     __/ |           </font><font color="#26A269">| Enjoy using this secured chat !</font>
<font color="#2AA1B3">                                    |___/            </font><font color="#26A269">| Enter &quot;help&quot; after signing for help</font>

Enter your username: Alice

-&gt; You are connected as <b>Alice</b>

Update : The connected users are:
	 -<b>Bob</b>

Bob
<font color="#A347BA">Your certificate has been sent to the recipient, awaiting a response from them</font>
-&gt; Certificate from Bob<font color="#26A269"> verified</font>
-&gt; You can now talk to <b>Bob</b>
<font color="#26A269">User Bob accept your certificate !</font>Let&apos;s send your first message to your new friend Bob
Bob : Hey, Alice there !
<font color="#2AA1B3">&gt;&gt;&gt; </font><font color="#33C7DE"><b>Bob</b></font> : Hey, I received your message!
help
<font color="#A2734C">-&gt; Help section of the Messenger application.</font>

<font color="#A2734C">+-------------------------------+</font>
<font color="#A2734C">|       Special commands        | </font>
<font color="#A2734C">+-------------------------------+</font>

<font color="#A2734C">[exit] | [quit] : Close the chat and exit the Application</font>
<font color="#A2734C">[help]          : Display this help</font>
<font color="#A2734C">[who]           : Display the list of users you can have a conversation with</font>

<font color="#A2734C">+-------------------------------+</font>
<font color="#A2734C">|   Connection to other users   | </font>
<font color="#A2734C">+-------------------------------+</font>

<font color="#A2734C">If you want to establish a connection with a user in the list of available</font>
<font color="#A2734C">users you received, you must send the user your signed certificate. To do so,</font>
<font color="#A2734C">just enter their username &quot;@userName&quot; in the chat. You should receive a </font>
<font color="#A2734C">message telling you you can now talk to each other. Once it&apos;s done, </font>
<font color="#A2734C">you MUST SEND THE FIRST MESSAGE to initiate conversation.</font>

<font color="#A2734C">+-------------------------------+</font>
<font color="#A2734C">|  Sending a message to a user  | </font>
<font color="#A2734C">+-------------------------------+</font>

<font color="#A2734C">After connection is established with another user (see in section above to</font>
<font color="#A2734C">see how to do it), you can send the user a message. To do so, you have to </font>
<font color="#A2734C">wright the other user name followed by &quot;:&quot; and then your message as shown</font>
<font color="#A2734C">on the example bellow.</font>

	<font color="#A2734C">Example : let the connection with Alice be established.</font>
	<font color="#A2734C">    &gt;&gt; Alice : Hello ! (or Alice:Hello !)</font>

who
The connected users are:
	 -<b>Bob</b><font color="#2AA1B3"> (friend)</font>
	 -<b>Alice</b> (you)
</pre>

<!--more-->



