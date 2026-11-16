# Beginner Project 02 - Web Server and TLS

## Subject

Host two websites with NGINX and protect them with HTTPS.

## Learning Goals

- Understand web servers, reverse proxies and virtual hosts.
- Understand HTTP requests and status codes.
- Learn the basic purpose of TLS certificates.
- Read web access and error logs.

## Mandatory Work

- Install NGINX on a Linux VM.
- Serve two different websites.
- Use hostnames such as `app1.cloudclub.test` and `app2.cloudclub.test`.
- Configure host-based routing in NGINX.
- Run a small backend service and expose it only through the reverse proxy.
- Generate a self-signed certificate for the lab.
- Enable TLS 1.2 or TLS 1.3 and redirect HTTP to HTTPS.
- Add useful security headers appropriate for a lab website.
- Demonstrate access and error logs.

## Deliverables

- Website files and backend source.
- NGINX configuration.
- Certificate-generation script or documented command.
- A README with start, stop, test and cleanup instructions.

## Validation

- Both hostnames show the correct website.
- HTTP redirects to HTTPS.
- The backend cannot be reached directly from outside the VM.
- `curl` can show the certificate and response headers.

## Estimated Time

One week.

<p align="center">
  <img src="../images/next-level.png" alt="Hit the next level" width="600">
</p>
