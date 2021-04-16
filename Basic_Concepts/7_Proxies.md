# Proxies
- Proxy is used to filter requests, log requests, conversion requests (such as adding and deleting headers, encryption, decryption, compressing resources, etc.)
- Also, the proxy can be used as a cache server. If many requests request the same resource, the proxy can cache this resource, and the proxy can directly return the result if there is a request for this resource next time

## Proxy Server 类型
- **Open Proxy**
  - Anonymous Proxy: hide user IP
  - Trаnspаrent Proxy: Cache website
- **Reverse Proxy**
  - On behalf of the server-side, the client does not need to know which server the proxy is connected to. In short, after the proxy gets the response, it returns to the client
  - Nginx is a reverse proxy with good performance

## API Gateway
- Very similar to the Proxy function
- It has more functions than Proxy, such as higher security level, custom API, Load balancing, Throttling, etc.
- API Gateway is a more advanced API Proxy
