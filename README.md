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
*Ref 2: KQL query used to isolate C2 communication from HTTP logs*
