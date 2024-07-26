# Common Network Ports and Services

This document provides a table of commonly used network ports and their associated services. This list can be useful for network configuration, firewall rules, and general reference.

| Port Number | Service/Protocol      | Description                                |
|-------------|------------------------|--------------------------------------------|
| 20          | FTP Data               | File Transfer Protocol (Data Transfer)     |
| 21          | FTP                    | File Transfer Protocol (Control)           |
| 22          | SSH                    | Secure Shell (Remote Login)                |
| 23          | Telnet                 | Telnet (Remote Login)                      |
| 25          | SMTP                   | Simple Mail Transfer Protocol              |
| 53          | DNS                    | Domain Name System                         |
| 67          | DHCP                   | Dynamic Host Configuration Protocol (Server)|
| 68          | DHCP                   | Dynamic Host Configuration Protocol (Client)|
| 80          | HTTP                   | Hypertext Transfer Protocol                |
| 110         | POP3                   | Post Office Protocol v3                    |
| 143         | IMAP                   | Internet Message Access Protocol           |
| 443         | HTTPS                  | HTTP Secure                                |
| 445         | SMB                    | Server Message Block (File Sharing)        |
| 587         | SMTP                   | SMTP with STARTTLS                         |
| 993         | IMAP                   | IMAP over SSL/TLS                          |
| 995         | POP3                   | POP3 over SSL/TLS                          |
| 1433        | MS SQL Server           | Microsoft SQL Server (Default)             |
| 3306        | MySQL                   | MySQL Database                             |
| 3389        | RDP                    | Remote Desktop Protocol                    |
| 5432        | PostgreSQL              | PostgreSQL Database                        |
| 6379        | Redis                   | Redis Database                             |
| 8080        | HTTP (Alternate)       | Alternate HTTP port (used by many web servers) |
| 8443        | HTTPS (Alternate)      | Alternate HTTPS port                       |

## Notes

- Ports are typically used by services for communication over a network.
- Some ports may be used by multiple services depending on the configuration.
- Always ensure that your firewall and network security policies align with the ports and services you intend to use.


