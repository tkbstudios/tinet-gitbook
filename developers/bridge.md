# 🌉 BRIDGE

The bridge is a way to bridge your serial connection to a TCP server.

***

The bridge contains the following built-in features not available on the TCP server:

* HTTP requests (GET, POST, PUT, PATCH and DELETE)
* On-bridge debugging
* Client updating

### Bridge feature docs

<details>

<summary>HTTP requests</summary>

You can do an HTTP request by doing the next serial command to the bridge:

```
HTTP_<method>***<url>***<headers>***<body>
```

* method: GET, POST, PUT, PATCH or DELETE
* url including scheme (http or https, ex. https://tinet.tkbstudios.com/)
* headers: correctly formatted headers
* body: correctly formatted body

This method returns the raw content bytes.

</details>

<details>

<summary>On-bridge debugging</summary>

Sending the following line will print the debug information to the bridge console:

```
LDBG_<message>
```

</details>

<details>

<summary>Client updating</summary>

By sending the following command to the bridge, you will receive a chunk of 512 bytes of the newest client file.

```
UPDATE_CLIENT:<version>
```

* version: prerelease or&#x20;

After receiving the 512 bytes, send UPDATE\_CONTINUE to the bridge to receive the next 512 bytes, etc..

If all the bytes were sent, the bridge will send UPDATE\_DONE and you can stop waiting for the bytes.

</details>
