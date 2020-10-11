# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/ue_wifi_schema.proto](#proto/ue_wifi_schema.proto)
    - [WiFiSchema](#openschema.schema.wifi.WiFiSchema)
    - [WiFiSchema.WiFiAPPSchema](#openschema.schema.wifi.WiFiSchema.WiFiAPPSchema)
    - [WiFiSchema.WiFiActiveQoSSchema](#openschema.schema.wifi.WiFiSchema.WiFiActiveQoSSchema)
    - [WiFiSchema.WiFiIPSchema](#openschema.schema.wifi.WiFiSchema.WiFiIPSchema)
    - [WiFiSchema.WiFiMACSchema](#openschema.schema.wifi.WiFiSchema.WiFiMACSchema)
    - [WiFiSchema.WiFiPHYSchema](#openschema.schema.wifi.WiFiSchema.WiFiPHYSchema)
    - [WiFiSchema.WiFiPassiveQoSSchema](#openschema.schema.wifi.WiFiSchema.WiFiPassiveQoSSchema)
    - [WiFiSchema.WiFiSecuritySchema](#openschema.schema.wifi.WiFiSchema.WiFiSecuritySchema)
    - [WiFiSchema.WiFiUsageSchema](#openschema.schema.wifi.WiFiSchema.WiFiUsageSchema)
    - [WiFiSchema.WifiScanResultSchema](#openschema.schema.wifi.WiFiSchema.WifiScanResultSchema)
    - [WiFiSchema.WifiScanResultSchema.WifiAp](#openschema.schema.wifi.WiFiSchema.WifiScanResultSchema.WifiAp)

    - [WiFiSchema.WiFiConnectionStatusSchema](#openschema.schema.wifi.WiFiSchema.WiFiConnectionStatusSchema)
    - [WiFiSchema.WiFiPHYSchema.WiFiStandard](#openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WiFiStandard)
    - [WiFiSchema.WiFiPHYSchema.WifiChannelWidth](#openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WifiChannelWidth)
    - [WiFiSchema.WiFiSecuritySchema.WiFiSecurity](#openschema.schema.wifi.WiFiSchema.WiFiSecuritySchema.WiFiSecurity)




<a name="proto/ue_wifi_schema.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/ue_wifi_schema.proto



<a name="openschema.schema.wifi.WiFiSchema"></a>

### WiFiSchema
UE WiFi schema represent a collection of metrics collected by UE related to active or available WiFi connections.
WiFi Schema is organized based on the network protocol stack.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| connection_status | [WiFiSchema.WiFiConnectionStatusSchema](#openschema.schema.wifi.WiFiSchema.WiFiConnectionStatusSchema) |  | Current Status of WiFi Connection. Whether UE is connected to an AP, functioning as hotspot or there is a P2P connection. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiAPPSchema"></a>

### WiFiSchema.WiFiAPPSchema
Application layer characteristics of WiFi from UE point of view.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| dns4 | [string](#string) |  | list of IPv4 DNS Server |
| dns6 | [string](#string) |  | List of IPv6 DNS Server |
| captive | [bool](#bool) |  | Is a captive portal present on this AP. |
| easyconnect | [bool](#bool) |  | Is this an EasyConnect WiFi connection: https://www.wi-fi.org/discover-wi-fi/wi-fi-easy-connect. |
| fqdn | [string](#string) |  | What is the FQDN of the passpoint configuration. |
| passpoint | [bool](#bool) |  | Specify if current WiFi connection is passpoint. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiActiveQoSSchema"></a>

### WiFiSchema.WiFiActiveQoSSchema
QoS and QoE characteristics of WiFi actively measured by UE. UE should measure these metrics periodically and based on different triggers.
Often a speed test is used to measure active metrics.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| active_up_bw | [int64](#int64) |  | Actively measured upload speed of the current connection(KBps). |
| active_down_bw | [int64](#int64) |  | Actively measured download speed of the current connection(KBps). |
| active_latency | [int32](#int32) |  | Actively measured latency of the current connection. Also known as RTT(millisec). |
| active_jitter | [int32](#int32) |  | Actively measured jiter of the current connection. |
| active_packetloss | [int32](#int32) |  | Actively measured packet loss of the current connection(percentage). |
| active_rssi | [int32](#int32) |  | Recieved signal strength of the current wifi status. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiIPSchema"></a>

### WiFiSchema.WiFiIPSchema
IP layer characteristics of WiFi from UE point of view.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ipv4 | [string](#string) |  | IPv4 address assigned to WiFi interface. |
| ipv6 | [string](#string) |  | IPv6 address assigned to WiFi interface. |
| public_ipv4 | [string](#string) |  | Public IPv4 address of current WiFi connection. |
| public_ipv6 | [string](#string) |  | Public IPv6 address of current WiFi connection. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiMACSchema"></a>

### WiFiSchema.WiFiMACSchema
MAC layer characteristics of WiFi from UE point of view.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ssid | [string](#string) |  | SSID of the WiFi access point related to current status. |
| bssid | [string](#string) |  | BSSID of the WiFi access point related to current status. |
| ssid_hidden | [bool](#bool) |  | Indicated if the current ssid is hidden or not. |
| soft_ssid | [string](#string) |  | SSID of the UE, if UE is functioning as AP(aka personal hotspot or tethering) |
| soft_bssid | [string](#string) |  | BSSID of the UE, if UE is functioning as AP(aka personal hotspot or tethering) |






<a name="openschema.schema.wifi.WiFiSchema.WiFiPHYSchema"></a>

### WiFiSchema.WiFiPHYSchema
Physical layer characteristics of WiFi from UE point of view.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| max_rx | [int32](#int32) |  | Maximum physical recieve bandwidth. |
| max_tx | [int32](#int32) |  | Maximu physical send bandwidth. |
| freq | [int32](#int32) |  | Frquency related to the current wifi status. Also representing the channel used. |
| linkspeed | [int32](#int32) |  | Current physical link speed. |
| ceter_freq_0 | [int32](#int32) |  | Center frequency. |
| ceter_freq_1 | [int32](#int32) |  | Center frequency. |
| channel_width | [WiFiSchema.WiFiPHYSchema.WifiChannelWidth](#openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WifiChannelWidth) |  | WiFi channel width of the current WiFi connection. |
| wifi_standard | [WiFiSchema.WiFiPHYSchema.WiFiStandard](#openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WiFiStandard) |  | Standard of the current WiFi connection. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiPassiveQoSSchema"></a>

### WiFiSchema.WiFiPassiveQoSSchema
QoS and QoE characteristics of WiFi passively measured by UE. UE should measure these metrics periodically and based on different triggers.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| passive_up_bw | [int64](#int64) |  | Passively measured upload speed of the current connection(KBps). |
| passive_down_bw | [int64](#int64) |  | Passively measured download speed of the current connection(KBps). |
| passive_latency | [int32](#int32) |  | Passively measured latency of the current connection. Also known as RTT(millisec). |
| passive_jitter | [int32](#int32) |  | Passively measured jiter of the current connection. |
| passive_packetloss | [int32](#int32) |  | Passively measured packet loss of the current connection(percentage). |
| passive_rssi | [int32](#int32) |  | Recieved signal strength of the current wifi status. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiSecuritySchema"></a>

### WiFiSchema.WiFiSecuritySchema
Security and Encryption characteristics of WiFi from UE point of view.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| security | [WiFiSchema.WiFiSecuritySchema.WiFiSecurity](#openschema.schema.wifi.WiFiSchema.WiFiSecuritySchema.WiFiSecurity) |  | What is the security and Encryption technology used in the current WiFi connection. |






<a name="openschema.schema.wifi.WiFiSchema.WiFiUsageSchema"></a>

### WiFiSchema.WiFiUsageSchema
UE WiFi usage associated to a specific WiFi session.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sent_bytes | [int64](#int64) |  | Number of bytes sent. |
| recieved_bytes | [int64](#int64) |  | Number of bytes recieved. |
| sent_packet | [int64](#int64) |  | Number of packets(TCP and UDP) sent. |
| recieved_packet | [int64](#int64) |  | Number of packets(TCP and UDP) recieved. |
| session_start | [int64](#int64) |  | Start time of the current WiFi session. WiFi session can be refered to as MDO session too. |
| session_end | [int64](#int64) |  | End Time of the current WiFi/MDO session. |






<a name="openschema.schema.wifi.WiFiSchema.WifiScanResultSchema"></a>

### WiFiSchema.WifiScanResultSchema
Result of WiFi scanning perfomed by UE.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| scanned_ap | [WiFiSchema.WifiScanResultSchema.WifiAp](#openschema.schema.wifi.WiFiSchema.WifiScanResultSchema.WifiAp) | repeated | Report from UE&#39;s background scanning for WiFi networks. |






<a name="openschema.schema.wifi.WiFiSchema.WifiScanResultSchema.WifiAp"></a>

### WiFiSchema.WifiScanResultSchema.WifiAp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ssid | [string](#string) |  |  |
| bssid | [string](#string) |  |  |
| rssi | [int32](#int32) |  |  |
| operator_name | [string](#string) |  |  |
| venue_name | [string](#string) |  |  |
| standard | [WiFiSchema.WiFiPHYSchema.WiFiStandard](#openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WiFiStandard) |  |  |








<a name="openschema.schema.wifi.WiFiSchema.WiFiConnectionStatusSchema"></a>

### WiFiSchema.WiFiConnectionStatusSchema
Current status of UE WiFi connection.

| Name | Number | Description |
| ---- | ------ | ----------- |
| wifi_ap_connected | 0 |  |
| wifi_ap_disconnected | 1 |  |
| wifi_ap_connection_updated | 2 |  |
| wifi_local_hotspot | 3 |  |
| wifi_direct | 4 |  |
| wifi_aware | 5 |  |



<a name="openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WiFiStandard"></a>

### WiFiSchema.WiFiPHYSchema.WiFiStandard
WiFi standard.

| Name | Number | Description |
| ---- | ------ | ----------- |
| standard_legacy | 0 |  |
| standard_11n | 1 |  |
| standard_11ac | 2 |  |
| standard_11ax | 3 |  |
| others | 4 |  |



<a name="openschema.schema.wifi.WiFiSchema.WiFiPHYSchema.WifiChannelWidth"></a>

### WiFiSchema.WiFiPHYSchema.WifiChannelWidth
Channel Width characteristics of WiFi.

| Name | Number | Description |
| ---- | ------ | ----------- |
| channel_width_20 | 0 |  |
| channel_width_40 | 1 |  |
| channel_width_80 | 2 |  |
| channel_width_80_plus | 3 |  |
| channel_width_160 | 4 |  |



<a name="openschema.schema.wifi.WiFiSchema.WiFiSecuritySchema.WiFiSecurity"></a>

### WiFiSchema.WiFiSecuritySchema.WiFiSecurity


| Name | Number | Description |
| ---- | ------ | ----------- |
| security_open | 0 |  |
| security_wpa2psk | 1 |  |
| security_wpa3_sae | 2 |  |
| security_wpa3_sae_transition | 3 |  |
