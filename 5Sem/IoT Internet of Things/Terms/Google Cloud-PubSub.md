See [[Publish-Subscribe Architectures|pub-sub]] for general publish-subscribe architectures. For mere om google og pub-sub, se dette [link](https://cloud.google.com/architecture/connected-devices/device-pubsub-architecture?hl=en)
- Provides a globally durable message ingesiton service
- by creating **topics** for streams or channels, you can enable different components of your application to **subscribe** to specific streams of data without needing to construct subscriber-specific channels on each device.
- Many devices have limited ability to store and retry sending telemetry data.
	- **Cloud Pub/Sub** scales to handle data spikes that can occur when swarms of devices respond to events in the physical world, and buffers these spikes to help isolate them from applications monitoring the data.

![[image_Google Cloud-PubSub.png]]
