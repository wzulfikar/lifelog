> Thu, 18 May 2017 at 2:57:55 MYT

***Buy the book here:*** 
http://leanpub.com/web-hacking-101

## HTTP Methods
1. `GET`: While there are no HTTP police, typically `GET` requests should not be associated with any data altering functions, they should just retrieve and provide data.
- `HEAD`: identical to the `GET` request except the server ***must not return*** a message body in the response.
- `POST`: used to invoke some function to be performed by the server, as determined by the server.
- `PUT`: used when invoking some function but referring to an already existing entity.
- `DELETE`: just as it sounds, it is used to invoke a request for the remote server to delete a resource identified by the URI.
- `TRACE`: another uncommon method, used to reflect back the request message to the requester
- `CONNECT`: this method is actually reserved for use with a proxy (a proxy is a basically a server which forwards requests to other servers)- `OPTIONS`: used to request information from a server about the communication options available. For example, calling for OPTIONS may indicate that the server accepts `GET`, `POST`, `PUT`, `DELETE` and `OPTIONS` calls but not `HEAD` or `TRACE`.

- **CVSS**: The Common Vulnerability Scoring System (CVSS) is a free and open industry standard for assessing the severity of computer system security vulnerabilities. CVSS attempts to assign severity scores to vulnerabilities, allowing responders to prioritize responses and resources according to threat. Scores are calculated based on a formula that depends on several metrics that approximate ease of exploit and the impact of exploit. Scores range from 0 to 10, with 10 being the most severe
