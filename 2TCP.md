# OSI model

stands for Open Systems Interconnection model. it's a model that is used to describe how the data is sent between devices.

## Layers

there are 7 layers in the OSI model:

## Physical Layer

is the layer that is used to send the data physically. it's the layer that is used to send the data from one device to another. the data are processed in bits form in this layer.
devices that are used in this layer are: hubs, repeaters.

## Data Link Layer

is the layer that is used to send the data from one device to another. the data are processed in packets form in this layer.
devices that are used in this layer are: bridges, switches.
addresses that are used in this layer are: MAC addresses.

### MAC Addressing

stands for Media Access Control Addressing. it's the address that is used to identify a device in a network. every device has a unique MAC address. Mac addresses are 48 bytes long and are written in 12 hexadecimal digits. the first 6 digits are the manufacturer code, the last 6 digits are the device code.

## Network Layer

is the layer that is used to send the data from one device to another. the data are processed in packets form in this layer.
devices that are used in this layer are: routers.
addresses that are used in this layer are: IP addresses.

### IP Addressing

stands for Internet Protocol Addressing. it's the address that is used to identify a device in a network. every device has a unique IP address. IP addresses are 32 bytes long and are written in 4 decimal digits.
IP addresses are divided in 4 classes depending on the first digit of the IP address:
if the first digit is between 1 and 126, the IP address is class A.
if the first digit is between 128 and 191, the IP address is class B.
if the first digit is between 192 and 223, the IP address is class C.
if the first digit is between 224 and 239, the IP address is class D.
the other IP addresses are reserved for special uses.
like the following:

| Class | First Digit | Range | Number of Hosts | Number of Networks |
|-------|-------------|-------|-----------------|--------------------|
| A     | 1-126       | 1-126 | 16,777,214      | 127                |
| B     | 128-191     | 128-191 | 65,534          | 16,383             |
| C     | 192-223     | 192-223 | 254             | 2,097,151          |
| D     | 224-239     | 224-239 | -               | -                  |

## Transport Layer

is the layer that is used to send the data from one device to another. the data are processed in segments form in this layer.

## Session Layer

is the layer that is used to send the data from one device to another. the data are processed in sessions form in this layer.

## Presentation Layer

is the layer that is used to send the data from one device to another. the data are processed in presentations form in this layer.

## Application Layer

is the layer that is used to send the data from one device to another. the data are processed in applications form in this layer.

# TCP/IP model

stands for Transmission Control Protocol/Internet Protocol model. it's a model that is used to describe how the data is sent between devices.

## Layers

there are 4 layers in the TCP/IP model:

### Application Layer

is the layer that is used to send the data from one device to another. the data are processed in applications form in this layer.
applications that are used in this layer are: HTTP, FTP, SMTP, DNS.

### Transport Layer

is the layer that is used to send the data from one device to another. the data are processed in segments form in this layer.
protocols that are used in this layer are: TCP, UDP.

### Internet Layer

is the layer that is used to send the data from one device to another. the data are processed in packets form in this layer.

### Network Access Layer

is the layer that is used to send the data from one device to another. the data are processed in bits form in this layer.
devices that are used in this layer are: hubs, repeaters, bridges, switches.
