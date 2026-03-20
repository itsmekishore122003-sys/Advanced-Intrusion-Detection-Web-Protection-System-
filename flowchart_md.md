# SentinelShield Flowchart (Text-Based)

```
          +-------------------+
          |  Start Project    |
          +-------------------+
                    |
                    v
          +-------------------+
          |  Setup Environment|
          |  - VirtualBox     |
          |  - Kali Linux VM  |
          |  - Metasploitable |
          +-------------------+
                    |
                    v
          +-------------------+
          |  Connect Machines |
          |  - Network setup  |
          |  - Find IPs       |
          +-------------------+
                    |
                    v
          +-------------------+
          |   Access DVWA     |
          |  - Browser login  |
          |  - Reset DB       |
          |  - Set Low Security|
          +-------------------+
                    |
                    v
          +-------------------+
          | Perform Attacks   |
          |  - SQL Injection  |
          |  - XSS            |
          |  - Command Injection|
          |  - Brute Force    |
          +-------------------+
                    |
                    v
          +-------------------+
          | Collect Apache Logs|
          |  - /var/log/apache2|
          |  - access.log      |
          +-------------------+
                    |
                    v
          +-------------------+
          | Analyze Logs in   |
          | Splunk            |
          |  - Upload logs    |
          |  - Detect attacks |
          +-------------------+
                    |
                    v
          +-------------------+
          |   End Project     |
          +-------------------+
```

## Flow Summary
- Setup environment (Kali + Metasploitable)
- Connect both systems
- Access DVWA in browser
- Perform different attacks
- Collect logs from Apache server
- Analyze logs using Splunk
- Understand attack