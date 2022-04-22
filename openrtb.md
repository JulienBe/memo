- Required means technically required, but probably won't be enough for proper business logic.
- Recommended means that their inclusion is customary 

# 2.5

# [2.6](https://iabtechlab.com/wp-content/uploads/2022/04/OpenRTB-2-6_FINAL.pdf)

Introduces Ad Pods for CTV transactions, a structured User-Agent object and other minor enhancements.

### Ad Pods

An ad pod is the term describing an ad break of the type you'd see in a TV-like viewing experience or hear on a radio stream. 
An ad pod typically contains one or more in-stream creative assets that play out contiguously within a stream of video or audio content. 
Ad podding features in OpenRTB 2.6 build on capabilities in previous versions for including multiple ad requests within a single bid request object to indicate those ad requests are in some way related. 
Pod bidding signals communicate additional information about the pod & impression opportunities within the pod such as the sequence of the ad impressions, total pod length, maximum # of ads within a pod, multiple pod associations, and more.

### Structured User-Agent

|    Attribute   |    Type   |                                                               Description                                                                             |
+----------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
| device.app.sua | UserAgent | Structured user agent information. If both 'ua' and 'sua' are present in the bid request, 'sua' should be considered the more accurate representation |
+----------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------+

# 3.0

[OpenRTB](https://github.com/InteractiveAdvertisingBureau/openrtb/blob/master/OpenRTB%20v3.0%20FINAL.md#openrtb-principles-) is a living specification: New objects and attributes may be added and enumerated lists may be extended at any time

- A demand source with an "OpenRTB 3.0" implementation but must tolerate new fields or enumerated list values it is not expecting, such as from a newer release of OpenRTB 3.0.
- Likewise, supply sources should freely transmit new fields or enumerated list values (such as from a newer release) and must tolerate bid responses with new fields and enumerated list values it is not expecting

### [Layers](https://github.com/InteractiveAdvertisingBureau/openrtb/blob/master/OpenRTB%20v3.0%20FINAL.md#protocol-layers-)

To assist in reuse of objects across different specifications and to enable various aspects of the specification to evolve at different paces, a layered approach is being adopted as of OpenRTB v3.0

![protocol-layers](https://camo.githubusercontent.com/1be9166fd41862c9c07d16fa1fafc478b3670388734686ea60534a0e33270525/68747470733a2f2f64726976652e676f6f676c652e636f6d2f75633f69643d3171574b5770586e454357384b704567516831764f67594567714144494d797a5a)

![protocol-layers](https://camo.githubusercontent.com/ec744b6540fc625d63f40c26b796f2812725e18bcf78870b8aba0fc2b89cf619/68747470733a2f2f64726976652e676f6f676c652e636f6d2f75633f69643d3162356f4b38524633577145504d79506d5233576f31436e66696831314a4f6158)

##### Layer 2: Format

JSON is the default format for bid request. An exchange may also offer binary representations (e.g., compressed JSON, ProtoBuf, Avro, etc.)

##### Layer 4: Domain

The Domain Layer defines the objects on which the Transaction Layer operates; the media exchange being transacted. 
In a typical advertising auction, the bid request would contain domain objects in two places. 
First, the overall request would contain domain objects that describe the context for the sale such as the site or app, the device, and the user. 
Second, each item being offered for sale would contain domain objects that define the item such as impression and placement details, specifications, and restrictions. 
Each bid in a response would include domain objects that define the media to be delivered to the user if the auction is won.

