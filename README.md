# qcogen
QoS Config Generator

Generates QoS configuration including ACLs, Classes and Policies from an Excel file.

Leverages Areas - specific scopes where particular traffic may be seen and thus QoS consifuration is necessary. 

Arguments:
QoS Flows filename, if not supplied, uses qos_flows.xlsx in the current directory by default.

Output directory (will be created if doesn't exist): _output
