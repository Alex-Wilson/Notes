| DNS Record | Full Name                                                       | Purpose                                                                                                                                                                                                   |     |     |     |
| ---------- | --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- |
| A          | Address Record                                                  | Used to map a hostname to its corresponding IPv4 address.                                                                                                                                                 |     |     |     |
| AAAA       | IPv6 Address Record                                             | Used to map a hostname to its corresponding IPv6 address                                                                                                                                                  |     |     |     |
| CNAME      | Canonical Name Record                                           | Used when you want multiple domain names to point to the same location or when you want to associate a subdomain with the same IP address as the parent domain.                                           |     |     |     |
| MX         | Mail Exchange Record                                            | Used to direct email traffic to the appropriate mail server for a domain.                                                                                                                                 |     |     |     |
| TXT        | Text Record                                                     | Used for various purposes such as domain verification, SPF (Sender Policy Framework) configuration, and DKIM (DomainKeys Identified Mail) authentication.                                                 |     |     |     |
| NS         | Name Server Record                                              | Used to delegate control of a domain to specific DNS servers.                                                                                                                                             |     |     |     |
| PTR        | Pointer Record                                                  | Used to associate an IP address with a domain name, primarily used in reverse DNS resolution                                                                                                              |     |     |     |
| SRV        | Service Record                                                  | Specifies the location of a specific service or resource in a domain.                                                                                                                                     |     |     |     |
| SPF        | Sender Policy Framework                                         | Specifies the authorized mail servers for sending emails on behalf of a domain, preventing email spoofing.                                                                                                |     |     |     |
| DKIM       | DomainKeys Identified Mail                                      | Provides a method for email authentication by adding a digital signature to outgoing messages, allowing the recipient server to verify the message's integrity and authenticity.                          |     |     |     |
| DMARC      | Domain-based Message Authentication, Reporting, and Conformance | Enables email domain owners to specify policies for email authentication, handling of failed messages, and receiving reports on email activity, helping prevent email impersonation and phishing attacks. |     |     |     |

