# Network Traffic Investigation: Suspected Reverse Shell Activity

A network traffic analysis project investigating suspicious TCP communication using Wireshark.

## Overview

This investigation examines a packet capture (`external.pcapng`) containing suspicious communication over TCP port 4444.

TCP stream analysis revealed command interaction between two endpoints, including Windows commands such as `whoami` and `ipconfig`. The observed communication pattern is consistent with reverse-shell activity.

## Objectives

- Identify suspicious TCP connections.
- Analyze connection establishment and communication direction.
- Examine TCP streams for command execution evidence.
- Identify the affected endpoint and exposed system information.
- Assess potential security implications and recommend defensive measures.

## Tools Used

- **Wireshark** — Network protocol and packet analysis.
- **TCP Stream Analysis** — Inspection of application-level communication.
- **PCAP** — Network traffic evidence.

## Key Findings

| Category | Finding |
|---|---|
| Protocol | TCP |
| Port | 4444 |
| Windows endpoint | 192.168.132.238 |
| Remote endpoint | 192.168.132.242 |
| Commands observed | `whoami`, `ipconfig` |
| Identified account | `desktop-tu9c8dk\emp10` |
| Activity assessment | Suspected reverse shell |

### Observed Communication

1. The Windows endpoint initiated a TCP connection to the remote endpoint.
2. The remote endpoint transmitted commands through the established connection.
3. The Windows endpoint returned command output.

This behavior is consistent with reverse-shell communication.

## Evidence

The investigation includes Wireshark screenshots documenting:

- Initial TCP connection establishment.
- TCP stream contents showing command interaction and output.

## Recommendations

- Investigate the remote endpoint and validate its ownership.
- Review Windows security and process execution logs.
- Examine potential persistence mechanisms.
- Investigate related network traffic.
- Restrict unauthorized outbound connections.
- Preserve relevant forensic evidence.

## Limitations

The conclusions are based on the supplied packet capture. The available evidence does not independently establish the operator's identity, initial access method, data exfiltration, persistence, or compromise of additional systems.

## Report

The detailed investigation report is available in the `report/` directory.

## Disclaimer

This project was conducted for cybersecurity learning and defensive investigation purposes using a provided training packet capture. Findings describe observed network behavior and should not be interpreted as confirmation of a real-world compromise.
