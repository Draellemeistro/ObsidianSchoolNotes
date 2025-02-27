> [!NOTE] **wildcards provide a powerful mechanism for subscribing to multiple topics simultaneously.**

**in [[MQTT]] Subscribers can SUBSCRIBE TO TOPICS USING [[MQTT-wildcards|WILDCARDS]] to receive messages that match a specific pattern.**


#### There are two types of wildcards:
- **single level:** it is represented by **THE SYMBOL PLUS (+)**. It allows the replacement of a single topic level. By subscribing to a topic with a single-level wildcard, any topic that contains an arbitrary string in place of the wildcard will be matched
	- _FOR EXAMPLE,_ a subscription to **myhome/groundfloor/+/temperature** can produce the following results:
		- _myhome/groundfloor/**livingroom**/temperature_
		- _myhome/groundfloor/**kitchen**/temperature_
- **Multi-level:** the multi-level wildcard covers multiple topic levels. It is represented by **THE HASH SYMBOL (\#)** and must be placed as the last character in the topic, preceded by a forward-slash.
	- When a client subscribes to **a topic with a multi-level wildcard**, it receives all messages of a topic that **begins with the pattern before the wildcard character**, **regardless of the length or depth of the topic.**
	- if the topic specified as **"\#" alone,**  the client receives **all messages** sent to the [[MQTT]] broker [[broker]]

###### Single level [[MQTT-wildcards|wildcard]] example
![[image files etc/img5sem/cloud images/image_MQTT.png]]
###### Multi-level [[MQTT-wildcards|wildcard]] example
![[image files etc/img5sem/cloud images/image_MQTT-1.png]]