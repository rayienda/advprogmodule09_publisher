a. How much data your publisher program will send to the message broker in one run?

The program sends five messages, each consisting of a serialized UserCreatedEventMessage using Borsh. Each message contains a user ID and a user name, with an estimated size of around 24 bytes. In total, the program sends approximately 120 bytes of data.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

The URL being in both the publisher and subscriber programs means that they are connecting to the same RabbitMQ message broker. The first guest is the username, and the second guest is the password used to authenticate. The localhost part tells the program to connect to a broker running on the same machine, and 5672 is the default port used by RabbitMQ to handle AMQP connections. This setup ensures that both the publisher and subscriber are communicating with the same broker instance.

- Running RabbitMQ as message broker
![rabbitMQ_overview.png](images/rabbitMQ_overview.png)

- Sending and processing event.
![sending_processing.png](images/sending_processing.png)

- Monitoring chart based on publisher.
![monitoring_chart.png](images/monitoring_chart.png)
  The spike in the message rate chart happened when the publisher was run. It shows that messages were successfully sent to the queue and immediately consumed. This confirms that the publisher and consumer are working correctly with RabbitMQ.


