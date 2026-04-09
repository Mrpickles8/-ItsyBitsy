# -ItsyBitsy

## Objective
Investigate a potential C2 beaconing activity using Elastic SIEM. The goal was to analyze HTTP traffic logs to identify a compromised host communicating with a command and control server, extract IOCs, and determine the scope of the infection.

### Skills Learned
- Elastic SIEM query writing (KQL)
- C2 beaconing pattern recognition (periodic HTTP requests)
- HTTP traffic log analysis
- IOC extraction (C2 IP, URI, user-agent, beacon interval)
- Incident scope determination

### Tools Used
- Elastic SIEM / Kibana
- KQL (Kibana Query Language)
- HTTP log analysis
- VirusTotal for C2 IP reputation

## Steps
Investigation started with querying Elastic SIEM for unusual HTTP traffic patterns using KQL. Periodic requests to a single external IP at consistent intervals were identified as C2 beaconing behavior. The malicious URI, user-agent string, and beacon interval were extracted as IOCs. The C2 IP was cross-referenced against VirusTotal, confirming known malicious infrastructure. The scope was determined by identifying all internal hosts communicating with the same C2 endpoint.

*Ref 1: Kibana dashboard showing periodic HTTP beaconing pattern*

<img width="692" height="673" alt="P1" src="https://github.com/user-attachments/assets/f59aa427-f640-4021-b43d-dab051261ef3" />

<img width="883" height="313" alt="p2" src="https://github.com/user-attachments/assets/446fac21-10dc-4de0-b94d-f35b74275586" />


*Ref 2: KQL query used to isolate C2 communication from HTTP logs*
<img width="561" height="90" alt="P3" src="https://github.com/user-attachments/assets/45bc852b-246a-4449-b6fb-16afdae6f73f" />

<img width="785" height="93" alt="P4" src="https://github.com/user-attachments/assets/aeb05409-bd0e-4e99-a4b5-6f9a8170e36d" />

<img width="786" height="76" alt="P5" src="https://github.com/user-attachments/assets/2dbe589a-dd46-4c0f-9fbe-d16b33f192a7" />





