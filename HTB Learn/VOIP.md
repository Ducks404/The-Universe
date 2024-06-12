> TCP 5060/5061 - Session Initiation Protocol
> TCP 1720 - H.323

## Session Initiation Protocol
> initiating, maintaining, modifying, and terminating real-time sessions

| **Method** | **Description**                                                                                                    |
| ---------- | ------------------------------------------------------------------------------------------------------------------ |
| `INVITE`   | Initiates a session or invites another endpoint to participate.                                                    |
| `ACK`      | Confirms the receipt of an INVITE request.                                                                         |
| `BYE`      | Terminate a session.                                                                                               |
| `CANCEL`   | Cancels a pending INVITE request.                                                                                  |
| `REGISTER` | Registers a SIP user agent (UA) with a SIP server.                                                                 |
| `OPTIONS`  | Requests information about the capabilities of a SIP server or user agent, such as the types of media it supports. |
The OPTIONS request can probe a SIP server or user agent for information or test its connectivity and availability.

It is possible to discover a `SEPxxxx.cnf` file, where xxxx is a unique identifier, is a configuration file used by `Cisco Unified Communications Manager`, formerly known as `Cisco CallManager`, to define the settings and parameters for a `Cisco Unified IP Phone`. The file specifies the phone model, firmware version, network settings, and other details.