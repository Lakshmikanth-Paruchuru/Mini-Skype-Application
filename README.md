# Mini-Skype-Application
A publish/subscribe model used in implementation of Skype network
Install puTTy software to run the application.
Follow the below steps:


	Broker Server:
•	To compile the “broker.c”, type gcc broker.c –o b –lnsl –lsocket –lresolv –lpthread.
•	To run ./b
•	It will list all the active broker ports. Eg: 5101, 5102, etc.
•	The broker server has now started to listen for publishers/subscribers.

	Publisher:
•	To compile a publisher program on a different terminal, type
 gcc publisher.c –o p –lnsl –lsocket –lresolv –lpthread
•	To run, type ./p 127.0.0.1 5101
•	It will ask for Publisher’s port, here you have to type publisher’s port number other than active broker’s port numbers stated above.
•	Type number of services that a publisher wants to provide.
•	Mention the service’s number by pressing ENTER after every input. (Enter the numeric input, 1-25)
•	Another thread will wait for any connection from the subscriber. Denoted as “Waiting”.

	Subscriber:
•	To compile a publisher program on a different terminal, type
 gcc sub.c –o s –lnsl –lsocket –lresolv –lpthread
•	To run, type ./s 127.0.0.1 5104 OR ./s “different IP” “Active broker’s port number list”
•	It will show the list of all services that was in the requirement, subscriber can subscribe from that list by entering the number of that service.
•	After entering the service number, the output will contain Publisher’s port number that provides the service and the path between publisher and subscriber. Eg:
6666->|5101->5102|5102->5103|5103-5104|.
Publisher’s port number that provides the service asked = 6666
Path = |5101->5102|5102->5103|5103-5104|
•	Now subscriber is directly connected with the publisher with the appropriate port number and then you need to enter the service you want from that publisher. Denoted as “Service has been provided”.
