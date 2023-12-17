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

* Launch your favorite TINET-powered program

{% hint style="warning" %}
If anything fails, download the latest release of the TINET-powered program, reset your keyfile key on the web dashboard, download your keyfile (NetKey.8xv) and update the bridge.

Transfer these 2 files over again to your calculator while also overwriting the previous ones.
{% endhint %}

* Run the python bridge using`python3 tinet-bridge.py` (if downloaded tinet-bridge.exe for windows, double click it)
* You may have to select the correct serial/COM port manually.

<details>

<summary>How to find the COM port on windows?</summary>

On Windows, you can find the matching COM port like this:

`(Open Device Manager (Start → Control Panel → Hardware and Sound → Device Manager) Look in the Device Manager list, open the category "Ports", and find the matching COM Port)`

A COM port looks like this: COM1, COM2, COM3, etc..

</details>

* Follow the instructions on your calculator in the TINET-powered program.

### Common issues that could rarely happen

<details>

<summary>ALREADY_CONNECTED</summary>

This happens when you already have a session on the TINET server. Wait 5 minutes and the session will expire.

</details>
