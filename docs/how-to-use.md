---
description: This page explains how to use TINET to get started quickly
---

# ❓ How To Use

{% hint style="warning" %}
Please follow every step for everything to work fine
{% endhint %}

{% content-ref url="installation.md" %}
[installation.md](installation.md)
{% endcontent-ref %}

* Open the TINET program on your calculator.

{% hint style="warning" %}
If you see a QR code when you try to log in, download the latest release (TINET.8xp), reset your keyfile key and download your keyfile (NETKEY.8xv).

Transfer these 2 files over again to your calculator while also overwriting the previous one.
{% endhint %}

* Run the python bridge using`python3 tinet-bridge.py`
* You may have to select the correct serial/COM port manually.

<details>

<summary>How to find the COM port on windows?</summary>

On Windows, you can find the matching COM port like this:

`(Open Device Manager (Start → Control Panel → Hardware and Sound → Device Manager) Look in the Device Manager list, open the category "Ports", and find the matching COM Port)`

A COM port looks like this: COM1, COM2, COM3, etc..

</details>

* On your calculator in TINET press \[enter] after you see internet connected to login to TINET.&#x20;

### Common issues that could rarely happen

<details>

<summary>I don't see "internet connected"</summary>

If you don't see internet connected, please check your bridge if it is connected to the calculator AND the TCP server (tinethub.tkbstudios.com:2052).

</details>

<details>

<summary>I only see "bridge connected"</summary>

This means there was an issue opening the socket connection to the servers, this could be due to an active maintenance on the production infrastructure which doesn't always take long, you can always check the TINET Discord server for status updates.

This is not a case that happens often, usually the bridge raises an Exception and exits itself.

</details>

<details>

<summary>I don't see "bridge connected" and "internet connected"</summary>

There could be an issue with how you did it, try again.

</details>

<details>

<summary>It still doesn't work!! Even after I tried again!</summary>

Then open a post in #forum in the [discord server](https://discord.gg/f63fmqtvWb).

</details>
