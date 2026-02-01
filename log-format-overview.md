````md
# Overview of Log File Formats

Logs record events that happen on a system, application, or network. In cybersecurity, logs provide key details about activities across an organization, such as who signed into an application at a specific point in time, what actions were performed, and where those actions originated from.

As a security analyst, **log analysis** is the process of examining logs to identify events of interest, suspicious behavior, or malicious activity. Understanding how different log formats are structured is critical for uncovering key details during investigations and for effective SIEM analysis.

This document covers the following common log formats:
* JSON
* Syslog
* XML
* CSV
* CEF

---

## Purpose of Logs in Security

Logs help security teams to:
* Detect malicious activity
* Investigate security incidents
* Correlate events across systems
* Support compliance and auditing
* Perform root cause analysis

Logs are one of the most important data sources in a Security Operations Center (SOC).

---

## JavaScript Object Notation (JSON)

JavaScript Object Notation (JSON) is a file format used to store and transmit data. It is lightweight, easy to read, and easy to write. JSON is widely used in web technologies, APIs, and cloud environments.

JSON syntax is derived from JavaScript and commonly includes:
* Key-value pairs
* Commas
* Double quotes
* Curly brackets
* Square brackets

---

### Key-Value Pairs

A key-value pair represents two linked pieces of data: a key and its corresponding value. A key-value pair consists of a key, followed by a colon, and then a value.

Example:
```json
"Alert": "Malware"
````

For readability, it is recommended to include a space after the colon.

---

### Commas

Commas are used to separate multiple key-value pairs.

Example:

```json
"Alert": "Malware", "AlertCode": 1090, "Severity": 10
```

---

### Double Quotes

Double quotes are used to enclose string values.

Example:

```json
"Alert": "Malware"
```

Numeric values are not enclosed in quotes:

```json
"AlertCode": 1090
```

---

### Curly Brackets

Curly brackets define an object, which stores data as a comma-separated list of key-value pairs. JSON log entries start and end with curly brackets.

Example:

```json
"User": {
  "id": "1234",
  "name": "user",
  "role": "engineer"
}
```

---

### Square Brackets

Square brackets define arrays, which store ordered lists of values.

Example:

```json
["Administrators", "Users", "Engineering"]
```

---

### Security Use Cases for JSON

* Cloud audit logs
* API access logs
* EDR and XDR telemetry
* SaaS application logs

---

## Syslog

Syslog is a standard for logging and transmitting data. It can refer to three different capabilities:

* Protocol
* Service
* Log format

Syslog is the native logging format used in Unix and Linux systems and is commonly used by network devices.

---

### Syslog Protocol

* Used to transport logs to a centralized log server
* Uses port 514 for plaintext logs
* Uses port 6514 for encrypted logs (TLS)

---







