## Check DNS

```bash
dig NS <domain> +short
```


## Curl using specified DNS

```bash
# pull alpine linux with libcurl that supports custom DNS 
docker pull alpine/curl

# make request through specified DNS
docker run --rm alpine/curl --dns-servers <dns> <url>

# example
docker run --rm alpine/curl --dns-servers 8.8.8.8 https://andrejkolic.com
```
