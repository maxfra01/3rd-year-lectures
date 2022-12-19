# Streaming
---
Implementato con diversi protocolli ad esempio: [[OSI 4 - Strato Trasporto]], [[OSI 7 - Strato Applicazione]].
| UDP                                                                                      | HTTP                                                                                          | 
| ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Il rate di invio corrisponde a quello di encoding, dunque ho un rate di playing costante | Il video è ottenuto tramite un metodo GET                                                     |
| Potrebbe non andare oltre i firewall                                                     | Si trasmette al massimo rate sotto TCP                                                        |
| Corti delay per togliere il network jitter                                               | HTTP/TCP passa nei firewall                                                                   |
|                                                                                          | I delay di play possono essere elevati, e la velocità è fluttuante per il congestion controlo |

Un potenziamento dello streaming HTTP è il **DASH, Dynamic Adaptive Streaming over HTTP**.
Un video viene diviso in tanti **chunks**, ognuno dei quali è trattato indistantemente dagli altri.
