# 🌉 BRIDGE

The bridge is a way to bridge your serial connection to a TCP server.

***

{% hint style="danger" %}
HTTP is disabled by default in the bridge config (top of `tinet-bridge.py`),\
This was done to prevent attacks, only enable if you know what you're doing!

HTTP could allow an attacker to download files on your computer/bridge and execute malicious code!
{% endhint %}

The bridge contains the following built-in features not available on the TCP server:

* HTTP requests (GET, POST, PUT, PATCH and DELETE) (WIP)
* Client updating (WIP)

### Bridge feature docs

<details>

<summary>HTTP requests (WIP)</summary>

You can do an HTTP request by doing the next serial command to the bridge:

```
HTTP_<method> <URL> <headers> <body>
```

* method: GET, POST, PUT, PATCH or DELETE
* URL including scheme (http or https, ex. https://tinet.tkbstudios.com/)
* headers: correctly formatted JSON headers
* body: correctly formatted body

all fields should NOT contain any spaces!

This method returns the raw content bytes to the calculator.

</details>

<details>

<summary>Client updating (WIP)</summary>

By sending the following command to the bridge, you will receive a chunk of 512 bytes of the newest client file.

For this, your program must be registered by us in our database, the download link you provide us should be to a GitHub releases page, we will handle everything else.

```
UPDATE_CLIENT:<version>
```

After receiving the 512 bytes, send UPDATE\_CONTINUE to the bridge to receive the next 512 bytes, etc..

If all the bytes were sent, the bridge will send UPDATE\_DONE and you can stop waiting for the bytes.

</details>
