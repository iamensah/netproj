## Final Projects
#### Overview
- The final project constitute 25% of your continuous assessment.
- Make sure you follow the instructions given for each project carefully.
- Each group is made up of four (4) students maximum. Each group will have a leader and three other students.
- Each student __MUST__ join exactly one group.
- Check for your group below and join the corresponding team.

#### How to create/join teams
- A link to the project repository will be provided.
- Each __group leader__ upon clicking on the link should create a team with the group name and the project title. Example, `Group 1: Chat Application`.
- The other group members on visiting the link should join their specific teams. They should avoid creating a team.
- In all we should be expecting 18 different teams plus one additional team which no one should join.

#### Groupings and Assigned Tasks

| Group Name    | Group Members                                                     | Task  | Team Name               |
| ------------- |:-----------------------------------------------------------------:|:-----:| -----------------------:|
| Group 1       | __PS/ITC/14/0065__, PS/ITC/14/0010, PS/ITC/14/0009, PS/ITC/14/0029| 6     | Group 1: PyWeb          |
| Group 2       | __PS/ITC/14/0024__, PS/ITC/14/0061, PS/ITC/14/0048, PS/ITC/14/0040| 3     | Group 2: AsyncChat      |
| Group 3       | __PS/ITC/14/0011__, PS/ITC/14/0026, PS/ITC/14/0067, PS/ITC/14/0068| 4     | Group 3: FileTrans      |
| Group 4       | __PS/ITC/14/0015__, PS/ITC/14/0034, PS/ITC/14/0047, PS/ITC/14/0035| 4     | Group 4: FileTrans      |
| Group 5       | __PS/ITC/14/0039__, PS/ITC/14/0057, PS/ITC/14/0007, PS/ITC/14/0060| 3     | Group 5: AsyncChat      |
| Group 6       | __PS/ITC/14/0063__, PS/ITC/14/0037, PS/ITC/14/0006, PS/ITC/14/0021| 2     | Group 6: SoundServer    |
| Group 7       | __PS/ITC/14/0008__, PS/ITC/14/0013, PS/ITC/14/0028, PS/ITC/14/0038| 1     | Group 7: ChatCli        |
| Group 8       | __PS/ITC/14/0003__, PS/ITC/14/0064, PS/ITC/14/0020, PS/ITC/14/0005| 5     | Group 8: P2P            |
| Group 9       | __PS/ITC/14/0041__, PS/ITC/14/0023, PS/ITC/14/0004, PS/ITC/14/0032| 5     | Group 9: P2P            |
| Group 10      | __PS/ITC/14/0033__, PS/ITC/14/0012, PS/ITC/14/0014, PS/ITC/14/0058| 4     | Group 10: FileTrans     |
| Group 11      | __PS/ITC/14/0055__, PS/ITC/14/0017, PS/ITC/14/0019, PS/ITC/14/0001| 1     | Group 11: ChatCli       |
| Group 12      | __PS/ITC/14/0049__, PS/ITC/14/0066, PS/ITC/14/0059, PS/ITC/14/0022| 3     | Group 12: AsyncChat     |
| Group 13      | __PS/ITC/14/0043__, PS/ITC/14/0030, PS/ITC/14/0052, PS/ITC/13/0050| 6     | Group 13: PyWeb         |
| Group 14      | __PS/ITC/14/0053__, PS/ITC/14/0025, PS/ITC/14/0044, PS/ITC/14/0002| 2     | Group 14: SoundServer   |
| Group 15      | __PS/ITC/14/0051__, PS/ITC/14/0062, PS/ITC/14/0070, PS/ITC/14/0042| 5     | Group 15: P2P           |
| Group 16      | __PS/ITC/14/0016__, PS/ITC/14/0056, PS/ITC/14/0054                | 2     | Group 16: SoundServer   |
| Group 17      | __PS/ITC/14/0050__, PS/ITC/14/0072, PS/ITC/13/0052                | 1     | Group 17: ChatCli       |
| Group 18      | __PS/ITC/14/0045__, PS/ITC/14/0036, PS/ITC/14/0046                | 6     | Group 17: PyWeb         |

> Note: Index numbers that are bold within the above table shall serve as your group leaders.


#### Project Ideas:
### 1. Command Line Chat System (ChatCli)
Create a single-threaded chat system (server &amp; client) meeting the following specifications:

- Entirely ascii protocol (below)
- Unlimited simultaneous connections (well, OK, unlimited within the operating  system and memory constraints)
- Any line beginning with a `~` is a command line (below)
- Any non-command line sent by a client should be repeated to all other clients  preceded with the user's name and a colon.
- Any line beginning with `@<username>` should be repeated to only the client with the specified username.
- The only type of lines received by the client, after the banners, will be  lines which begin with a user name and a colon.
- Unlimited length lines should be supported (again subject to usual constraints)

Your server should implement the following case sensitive command set (note, any quotes or other emphasis below are for readability and are not part of the protocol):

- __`~HELP`__ -- print a list of the available commands
- __`~NAME: <username>`__ -- the username is terminated by the first whitespace (cannot contain spaces). If this username is already in use the server should indicate so with a message and terminate the connection. Can only be issued once by a client.
- __`~EMAIL: <e-mail address>`__ -- the e-mail address of this user terminated by a newline character
- __`~GETEMAIL: <username>`__ -- return a single line with the format _`<username>: e-mail`_ where _`e-mail`_ is replaced by the __e-mail__ address of the specified user, _`unknown`_ if the user has not indicated an e-mail address, or _`no such user`_ if the specified user is not on the system.

After a connection is received send a single line ASCII banner indicating the __`program name and date`__ to the client. Subsequently send a single line __`Please indicate your name with the ~NAME: command`__ so that simple clients can be used.

The first line supplied by the client must be a __`~NAME:`__ command or the connection should be closed due to protocol violation.

### 2. Command Line Animal Sound System (SoundServer)
Create a system (server &amp; client) that uses TCP sockets to implement a service that returns the sounds made by animals. 

The server, which will be called __`SoundServer`__, will operate as follows:

- Return the sound made by animals named by a client after the client connects to the server using the __`SOUND`__ instruction.
- Accepts a __`STORE`__ message used for storing new (animal, sound) pairs.
- Accepts a __`QUERY`__ message used to ask which animals it knows.
- Accepts a __`BYE`__ message that results in closing of the current session between the client and the server.
- Accepts an __`END`__ message that results in closing of the current session and termination of the server.

Operation of the client and the server is as follows:

- When the server starts, it initially stores five pairs of query containing an animal’s name and the sound it makes, _e.g. ‘dog’ and ‘woof’_. The server stores this start-up data in an internal data structure.
- A client connects to the server using an IP and a port number. 
- The server is __NOT__ required to concurrently interact with clients. 
- The server puts new clients in a __queue__. As soon as a connected client terminates its connection, the server automatically connects the first client in the queue.

The client, which will be called __`SoundClient`__ uses __`SOUND`__, __`STORE`__, __`QUERY`__, __`BYE`__ and __`END`__ commands to instruct the server. The client program will be capable of sending any of these messages on instruction from the user.

Operation of the client-server pair is as follows:

- Requesting sounds is performed when the client sends a string, representing the name of an animal, terminated by a newline character. On receipt of such a string, the server returns the sound made by the animal specified by the client, or indicates that it does not know that animal, as shown in the following examples.

```sh
Client: DOG
Server: A DOG SAYS WOOF
Client: CAT
Server: I DON’T KNOW CAT
```

- __`STORE <animal>, <sound>`__: This message stores in the server memory, animal name and sound made by the animal. A typical message sequence would be as follows:
    
```sh
Client: STORE CAT, MEOW
Server: STORE OK
```

- If the server already knows the animal specified by the first argument, the sound specified by the second argument replaces that stored by the server. If the server’s storage is full (i.e. it already knows 15 animals and the sound they make), and the newly-specified animal is not already known to the server, the server returns __`STORE FULL`__.
- __`QUERY`__: This returns the names of all the animals stored in the server’s memory. A typical message sequence would be as follows:

```sh
Client: QUERY
Server: DOG, HORSE, SNAKE, COW, SHEEP, CAT
```

- __`END`__: If there is no client in the queue, the END command terminates the server else, the client session is terminated and the first client in the queue is connected. Note, any animal sound pairs added by the client are not saved, and the server reverts to the initial five pairs. A typical message sequence would be as follows:

Current Client

```sh
Client: END
Server: DISCONNECTED # if there is a client in the queue
_OR_
Server: TERMINATING ... # if there is no client in queue
```

First Client in Queue

```sh
Server: YOU ARE NOW CONNECTED!!!
```

> Note that, regardless of the case of characters typed by the user of the SoundClient, the characters are sent to the SoundServer as upper case.

### 3. Command Line Asynchronous Chat System (AsyncChat)
Develop comprehensive client-server messaging system.

- Application has basic security features of a chat room
- Application has support for broadcast and point to point messages
- Includes concepts of asynchronous messaging
- Clients communicate with each other through “commands” sent to centralized server

##### Authentication Features:
- Sever maintains text file with username password
- Clients authenticate themselves and log into the system
- After 3 consecutive unsuccessful login attempts, the servers blocks the IP for that user for 60 seconds.
- Prohibit simultaneous duplicate logins. Eg While Sasapuii is logged in, restrict Sasapuii from other terminals.

##### Messaging Features:
- __`whoelse`__ command: Displays name of other connected users.
- __`wholasthr`__ command: Displays name of users connected within last hour.
- __`broadcast <message>`__ command: The message is immediately displayed on the logged in users terminal.
- __``@<user> <message>`__ command: This message is sent only to a specific user.
- __`block <user>`__ or __`unblock <user>`__ command: It block or unblock other user(s) Based on this the private messages wont be delivered.
- __`logout`__ command: To enable logging off functionality.

##### Asynchronous messaging
- If a user is not available, such offline message are displayed when the user logs in next time.
- Only applicable for private messages.

### 4. Command Line File Transfer  System (FileTrans)
Develop a system to transfer files over a TCP/IP network socket connection. The server will be run as follows: 

- Server must be able to handle multiple client connections (all of which might be active at any given time).
- server needs to defend itself from attack and abuse. 
    - The server should not allow clients to: 
        - access forbidden files 
        - overwrite existing files on uploads
        - crash if a client starts misbehaving
    - The server needs to properly manage system resources (memory)
- The server should limit the number of simultaneous client connections and automatically disconnnect clients that appear to be idle. 

The client program should accept the following commands:

- __`connect <server> <port>`__ command: client connect to a server with the server-ip and port number. 
    
```sh
client> connect 192.168.5.80 10000
Connected to 192.168.5.80
Welcome to Onaapo's file server.
```

Once the client has connected to the server, the client should interactively get a directory listing, download and upload files, and close the connection.
    
- __`dir`__ command: list files on server

```sh
client> dir 
total 229
-rw-rw-r--   1 Onaapo  Onaapo       134 Dec 19 17:59 src
-rw-rw-r--   1 Onaapo  Onaapo        75 Dec 19 17:55 build
-rwxrwxr-x   1 Onaapo  Onaapo      5876 Dec 16 22:59 a.out
-rwxrwxr-x   1 Onaapo  Onaapo      9130 Dec 19 21:28 client
-rw-rw-r--   1 Onaapo  Onaapo       580 Dec 16 22:59 client.py
```

- __`put`__ command: transfer file from client to server

```sh
client> put spam  # Upload a file to the server 
Sent spam, 10672 bytes.
```

- __`get`__ command: transfer file from server to client

```sh
client> get client.py # Download an existing file from the server.
Received 'client.py' 580 bytes.
client> get foobar  # file not existing on from the server.
File not found.
client> get /etc/passwd #file not found on server
File not found.
```

- __`quit`__ command: disconnect from server

```client> quit 
Goodbye!
```

### 5. Command Line Peer-To-Peer File Sharing System (P2P)
Develop a peer-to-peer system for file sharing purposes. For a P2P network, every node (computer) will be running the exact same set of algorithms and code and there is no centralized server or otherwise special node to keep things organized. In the protocol you are to develop, there will be 9 types of messages exchanged between nodes. Each message type is identified by a 4-character string and may be accompanied with additional message data, summarized as follows:

- __`NAME`__: Requests a peer to reply with its _official_ peer id (_`host:port`_). When a peer receives a __`NAME`__ message (and no additional data), it simply responds by sending back its peer id, of the form _`host:port`_. Example:

```sh
[peer123]=> NAME
->>> 192.168.0.1:8900 
```

- __`LIST`__: Requests a peer to reply with the list of peers that it knows about. When a peer receives a __`LIST`__ message (and no additional data), it responds by first sending a message with the number of id's in its list of known peers. Then it sends additional messages, including a string with the peer id, host address, and port number (all three separated by whitespace) associated with each known peer in its list. Example:

```sh
[peer123]=> LIST
->>> Number of peers connected: 3
->>> 12345 192.168.0.3 7800
     67890 192.168.5.1 9000
     98765 192.168.7.3 7000
->>>
```

- __`JOIN pid host port`__: Requests a peer to add the supplied host/port combination, associated with the node identified by pid, to its list of known peers. A __`JOIN`__ message is accompanied with additional data specifying a sending peer id, IP address, and port number. The __`JOIN`__ message is used to request a peer to insert the sending node into its list of known peers. If the peer's list is already full, or the specified id is already in the list (or incorrect arguments are specified with the __`JOIN`__ message), then an __`ERRO`__ message is sent back in response. Otherwise, the remote node's information is added to the list and an acknowledgement is sent. Example: 

```sh
[peer123]=> JOIN 12345 192.168.0.3 7800
->>> Successful
[peer123]=> JOIN 12345 192.168.0.3 7800 # already in peer list
->>> ERROR3: Peer already in list
[peer123]=> JOIN 12345 192.168.0 7800 # wrong argument, ip is wrong
->>> ERROR4: Wrong IP argument
[peer123]=> JOIN 12345 192.168.152.70 9000 # peer list exceeded
->>> ERROR5:  Peer list is full
```

- __`QUER return-pid key ttl`__: Queries a peer to see if the peer has any record of a file name matching key. If so, send a message back to the node identified by _return-pid_; if not, propagate the query to all known peers with a decreased _ttl_ (time-to-live) value, unless _ttl_ is already 0. Example:

```sh
[peer123]=> QUER 123 myfile.txt 70 # successful query for myfile.txt 
->>> File: myfile.txt exists
[peer123]=> QUER 123 anotherfile.txt 70 # unsuccessful query for anotherfile.txt 
->>> ERROR1: File - anotherfile.txt does not exist.
```

- __`FGET filename`__: Download the specified _filename_ from a connected peer to the requested peer. The data of an FGET message consists of a file name. If the peer receiving the FGET message does not own a copy of the specified file or if it is not readable for some reason, an error reply is sent. Otherwise, the entire file is downloaded to the requested peer and a message with the file size sent to the requested peer.

```sh
[peer123]=> FGET myfile.txt # file exists
->>> myfile.txt successfully downloaded. You received 1kB of data.
[peer123]=> FGET notexist # file does not exist
->>> ERROR1: The file you requested does not exists. 
```

- __`QUIT pid`__: Indicate to a peer that the node identified by pid wishes to be unregistered from the P2P system. A __`QUIT`__ message, including a peer id in the data of the message, tells a peer to remove the specified node's information from its list of known peers as that node is preparing to leave the network. Note that, as is the case in most P2P protocols, node may also leave the network unexpectedly, so some sort of "stabilization" routine should be run by every peer node to periodically update its list of peers.

- __`ADD filename`__: Registers the specified file name as being locally stored on the peer. Shared files are stored in the same directory as the application's executable file.


### 6. HTTP Web Server (PyWeb)
Implement a sufficient part of the __HTTP 1.1__ protocol in your web server such that a user could download an unzipped version of [https://github.com/BlackrockDigital/startbootstrap-new-age/archive/gh-pages.zip](this test website) using any of the following web browsers: Chrome, Firefox, Safari, IE, and Edge. Your server should faithfully transmit any file requested by the web browser when downloading the demo website, which may include HTML, CSS, Javascript, or images. Once rendered by the browser, the website hosted by your web server should be indistinguishable when compared to the [https://blackrockdigital.github.io/startbootstrap-new-age/](site) hosted on the original web server. Any broken images, missing text, JavaScript warnings, etc... will be taken as an indication that your server is corrupting the files it transmits.  (Obviously, if the web server is corrupting files, then we cannot expect the web browser to be able to display a perfect-looking website). Your program should do the following:

- You must support web browsers sending requests using version 1.1 of the HTTP protocol, and accept connections (and deliver responses) via TCP.
- You must support the __GET__ request method from clients. Any other request that is not GET should produce a _`501: Not Implemented`_ error response. This is preferable to silently failing.
- You must support HTTP status codes __200 (OK), 404 (Not found), and 501 (Request method not implemented)__ as possible responses by your server.
- Your server should listen on any port either than _80_. In your web browser, access your server by specifying the port number in the URL, e.g. `http://localhost:port/file.html`

The following command-line arguments should be supported:

- __`--help`__: This argument will print out a helpful message describing what arguments the program takes
- __`--base=/path/to/directory`__: This argument allows you to specify the base directory where the website is stored on the server
- __`--port=####`__: This argument allows you to specify the port number the web server listens on.
