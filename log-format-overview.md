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

### Syslog Service

The syslog service:

* Receives logs from multiple sources
* Forwards logs to a central server
* Enables centralized log management

---

### Syslog Log Format

A syslog log entry consists of:

* Priority (PRI)
* Header
* Structured data (optional)
* Message

Example:

```text
<236>1 2022-03-21T01:11:11.003Z virtual.machine.com evntslog ID01
[user@32473 iut="1" eventSource="Application" eventID="9999"]
This is a log entry!
```

---

### Header

The header contains:

* Timestamp
* Hostname
* Application name
* Message ID

---

### Timestamp

Example:

```text
2022-03-21T01:11:11.003Z
```

* Date format: YYYY-MM-DD
* Time format: 24-hour
* Z indicates UTC timezone

---

### Structured Data

Structured data is enclosed in square brackets and written in key-value pairs.

Example:

```text
[user@32473 iut="1" eventSource="Application" eventID="9999"]
```

---

### Message

The message contains the detailed description of the event.

Example:

```text
This is a log entry!
```

---

### Priority (PRI)

The PRI field indicates the urgency of the event and is enclosed in angle brackets.

Example:

```text
<236>
```

Lower priority values indicate more urgent events.

---

### Security Use Cases for Syslog

* Firewall and router logs
* Switch and network device logs
* Linux system logs
* Centralized SOC monitoring

---

## XML (eXtensible Markup Language)

XML is a language and data format used to store and transmit structured data. It is the native file format for Windows systems and is commonly used for Windows Event Logs.

XML uses:

* Tags
* Elements
* Attributes

---

### Tags

Tags identify and store data.

* Start tag: `<tag>`
* End tag: `</tag>`

---

### Elements

Elements consist of tags and the data inside them. Every XML document must contain at least one root element.

Example:

```xml
<Event>
  <EventID>4688</EventID>
  <Version>5</Version>
</Event>
```

In this example:

* `<Event>` is the root element
* `<EventID>` and `<Version>` are child elements

---

### Attributes

Attributes provide additional information about elements and are included inside the tag.

Example:

```xml
<EventData>
  <Data Name='SubjectUserSid'>S-2-3-11-160321</Data>
  <Data Name='SubjectUserName'>JSMITH</Data>
  <Data Name='SubjectDomainName'>ADCOMP</Data>
  <Data Name='SubjectLogonId'>0x1cf1c12</Data>
  <Data Name='NewProcessId'>0x1404</Data>
</EventData>
```

---




