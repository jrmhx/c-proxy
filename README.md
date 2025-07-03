# Web Proxy with Caching

## Overview

This command-line tool implements a web proxy server with support for caching. It is designed to handle HTTP requests and optionally apply different cache replacement policies for improved performance.

## Build Instructions

- To compile the program, run:  
  ```bash
  make all
  ```

- To clean up object files, run:  
  ```bash
  make clean
  ```

## Running the Proxy

To launch the proxy server:

```bash
./proxy <port> [cache replacement policy]
```

### Examples:

- Run the proxy on port 8080 with the default cache replacement policy (LRU):
  ```bash
  ./proxy 8080
  ```

- Run the proxy with the LRU (Least Recently Used) cache policy:
  ```bash
  ./proxy 8080 LRU
  ```

- Run the proxy with the LFU (Least Frequently Used) cache policy:
  ```bash
  ./proxy 8080 LFU
  ```

## Testing Environment

This tool is compatible with **macOS** and **Linux** platforms.

### Recommended Browser: Firefox

Firefox is recommended due to its easy and precise proxy configuration:

1. Open **Settings** and search for "Proxy".
2. Choose **Manual proxy configuration**.
3. Set the HTTP proxy to `localhost` (127.0.0.1) and specify the port used by your proxy.
4. Navigate to `about:config` and set the following:
   - `network.proxy.allow_hijacking_localhost` → `true`
   - `browser.cache.disk.enable` → `false`
   - `browser.cache.memory.enable` → `false`

> ⚠️ Don’t forget to restore your cache settings after testing.

### Other Browsers

Browsers like Chrome and Safari require system-wide proxy settings, which can be less convenient for testing. If possible, use Firefox for a more streamlined experience with fine-grained control over HTTP requests.

## Benchmark

```bash
./driver.sh
```

