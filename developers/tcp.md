---
description: These are the TCP docs, here are all the TCP commands documented
---

# 🌐 TCP



<details>

<summary>TINET-TERM for developers</summary>

You can use [TINET-TERM](https://github.com/tkbstudios/tinet-term) to work on the TCP side of TINET if you are a developer that wants to build on TINET.

</details>

{% hint style="info" %}
Server address for the TCP server is the following:

* domain: tinethub.tkbstudios.com
* port: 2052
{% endhint %}

{% hint style="warning" %}
TCP side also has rate limiting, your command will be dropped if you send too much commands, your command will be dropped and won't be executed.
{% endhint %}

## Outgoing TCP commands

#### SERVER\_PING

* **Description**: Returns "PONG" to check if the server is still connected.

#### GPT:message (Work in Progress)

* **Description**: Allows communication with ChatGPT. Further details may be under development.

#### ACCOUNT\_INFO

*   **Description**: Returns account information in the following format:

    ```
    user_id;username;email;last_login;plan;total_requests;time_online;user_public
    ```

    * `user_id`: int
    * `username`: max. 18 chars
    * `last_login`: Epoch time
    * `plan`: "free", "pro" or "OG"
    * `total_requests`: int
    * `time_online`: seconds
    * `user_public`: 1 for true and 0 for false

#### RTC\_CHAT:recipient:message

* **Description**: Sends a message to the recipient, where `recipient` can be "global" for global messages or a friend's username for DM (DMs are work in progress).

#### GET\_BUCKET\_CONTENT:bucketname (Work in Progress)

* **Description**: Retrieves a list of files in the specified bucket, returning filenames.\
  `filename1;filename2;filename3`

#### GET\_BUCKET\_FILE:bucketname:filename (Work in Progress)

* **Description**: Retrieves the contents of a specific file from a bucket, returning file bytes.

#### DELETE\_BUCKET\_FILE: bucketname:filename (Work in Progress)

* **Description**: Deletes a file from a bucket, with success and error responses.

#### CREATE\_BUCKET:name (Work in Progress)

* **Description**: Creates a new bucket, with success and error responses.

#### DELETE\_BUCKET:bucketname (Work in Progress)

* **Description**: Deletes a bucket, with success and error responses.

#### UPLOAD\_TO\_BUCKET:bucketname:filename (Work in Progress)

* **Description**: Uploads a file to a bucket, with success and error responses.

#### LIST\_REPO:category (Work in Progress)

* **Description**: Lists repositories by category, returning filenames, with an error response.
* Categories: "games", "tools", "oiramlevels", "geodashlevels"

#### GET\_AD

*   **Description**: Retrieves an ad with the following format:

    ```
    id;url;title;description;image_url
    ```

#### SERIAL\_DISCONNECTED

* **Description**: Notifies the server that the calculator has been disconnected, triggering the login process for the bridge's auto-reconnect feature.

#### SERIAL\_CONNECTED

* **Description**: Sent when connecting to the TCP server, likely handled automatically.



## Incoming TCP data

#### RTC\_CHAT: recipient: timestamp: username: message

* This is received every time a message is being sent in TINET Chat.
* Recipient: username or a global chatroom name (global, etc.. more are coming later), max. 18 chars
* Timestamp is an epoch timestamp
* Username: max. 18 chars
* Message: limited to 300 chars (gets cut off by servers)

#### GAME\_INVITE: sender: game (Work In Progress)

* This is received every time a friend invites you to play a game
* sender: max. 18 chars and limited to friendlist
* game: name of the game (ex. tictactoe, chess, etc.. funnier games will be coming later), limited to 16 chars
