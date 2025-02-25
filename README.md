# Unicornscan
Unicornscan is a network scanning tool often used in penetration testing and security assessments. It is designed to gather information about hosts and services on a network, utilizing various scanning techniques.

### Installation

To install Unicornscan on Kali Linux, you can use the following command:

```bash
sudo apt-get update
sudo apt-get install unicornscan
```

### Basic Usage

The basic syntax for Unicornscan is:

```bash
unicornscan [options] <target>
```

### Common Options

- `-p <port>`: Specify the port or range of ports to scan.
- `-I`: Use ICMP scanning.
- `-r <number>`: Set the number of probes to send.
- `-v`: Enable verbose output.
- `-oA <basename>`: Output results in all formats with the specified basename.

### Examples

1. **Basic TCP Scan:**

   To scan a specific host on the default ports:

   ```bash
   unicornscan 192.168.1.1
   ```

2. **Scanning Specific Ports:**

   To scan for specific ports, such as 80 and 443:

   ```bash
   unicornscan -p 80,443 192.168.1.1
   ```

3. **Scanning a Range of IPs:**

   To scan a subnet (for example, 192.168.1.0/24):

   ```bash
   unicornscan 192.168.1.0/24
   ```

4. **Verbose Output:**

   For more detailed information during the scan:

   ```bash
   unicornscan -v 192.168.1.1
   ```

5. **Outputting Results:**

   To save the results in multiple formats:

   ```bash
   unicornscan -oA scan_results 192.168.1.1
   ```

### Additional Tips

- Always ensure you have permission to scan the target network.
- Use `man unicornscan` for more detailed options and configurations.
- Unicornscan can be combined with other tools for more extensive analysis.

Unicornscan is a powerful tool, but it may require some practice to fully utilize its capabilities effectively.



                                                    ALTERNATIVE
### Unicornscan Tool in Kali Linux

**Unicornscan** is a powerful network scanning tool designed for information gathering and security auditing. It allows users to perform asynchronous scans, making it faster than many traditional tools.

#### Installation
Unicornscan is typically included in Kali Linux by default. If it’s not installed, you can install it using:

```bash
sudo apt-get update
sudo apt-get install unicornscan
```

#### Basic Usage

The general syntax for Unicornscan is:

```bash
unicornscan [options] <target>
```

#### Common Options

- `-I`: Specify the interface to use.
- `-p`: Specify the port or port range to scan (e.g., `-p 80`, `-p 1-1000`).
- `-r`: Set the rate of packets sent (e.g., `-r 100`).
- `-v`: Enable verbose mode.
- `-o`: Output format (e.g., `-oA` for all formats).

#### Examples

1. **Basic TCP Scan on a Single IP**

   To perform a TCP scan on the target IP address:

   ```bash
   unicornscan -mT 192.168.1.1
   ```

2. **Scan Specific Ports**

   To scan specific ports (e.g., 22 and 80):

   ```bash
   unicornscan -mT 192.168.1.1:22,80
   ```

3. **Asynchronous Scan with Verbose Output**

   To run an asynchronous scan with verbose output on a range of ports:

   ```bash
   unicornscan -mT 192.168.1.1:1-1000 -v
   ```

4. **Scan a Network Range**

   To scan an entire subnet (e.g., `192.168.1.0/24`):

   ```bash
   unicornscan -mT 192.168.1.0/24
   ```

5. **Rate Limiting the Scan**

   To limit the scan rate to 100 packets per second:

   ```bash
   unicornscan -mT 192.168.1.1 -r 100
   ```

#### Notes

- **Permissions**: Running scans may require root permissions. Use `sudo` if necessary.
- **Legal Considerations**: Always ensure you have permission to scan the target network to avoid legal issues.

### Conclusion

Unicornscan is a versatile and efficient tool for network reconnaissance. With its ability to perform asynchronous scans, it can be a valuable asset in penetration testing and network security assessments.





                                                     ALTERNATIVE
The unicornscan tool in Kali Linux is a powerful network scanning and information gathering utility. It is primarily used for port scanning and service enumeration, which helps in identifying open ports and services running on target systems. Here's how you can use unicornscan and some examples:

1. **Port Scanning**:
   - Basic TCP port scan:
     ```
     unicornscan -mT -Iv 192.168.1.100
     ```
     This will perform a TCP connect scan on all ports of the target host `192.168.1.100`.
   - UDP port scan:
     ```
     unicornscan -mU -Iv 192.168.1.100
     ```
     This will perform a UDP scan on all ports of the target host `192.168.1.100`.

2. **Service Enumeration**:
   - Enumerate services running on open ports:
     ```
     unicornscan -mS -Iv 192.168.1.100
     ```
     This will perform a SYN scan and display the services running on the open ports of the target host `192.168.1.100`.

3. **OS Fingerprinting**:
   - Determine the operating system of the target:
     ```
     unicornscan -mT -Iv -p80,443 192.168.1.100
     ```
     This will perform a TCP connect scan on ports 80 and 443 of the target host `192.168.1.100` and attempt to determine the target's operating system.

4. **Scan Range of IP Addresses**:
   - Scan a range of IP addresses:
     ```
     unicornscan -mT -Iv 192.168.1.1-254
     ```
     This will perform a TCP connect scan on all IP addresses from `192.168.1.1` to `192.168.1.254`.

5. **Scan Specific Ports**:
   - Scan specific ports:
     ```
     unicornscan -mT -Iv -p22,80,443 192.168.1.100
     ```
     This will perform a TCP connect scan on ports 22, 80, and 443 of the target host `192.168.1.100`.

6. **Scan with Stealth Mode**:
   - Perform a stealthy scan:
     ```
     unicornscan -mT -Iv -r50 192.168.1.100
     ```
     This will perform a TCP connect scan on the target host `192.168.1.100` with a rate of 50 packets per second, making the scan less detectable.

The unicornscan tool provides a wide range of options and features, allowing you to customize your scans according to your specific requirements. It is a valuable tool in the arsenal of a security professional or a penetration tester for gathering information about target systems.





                                                            ALTERNATIVE
Unicornscan is a powerful information gathering and scanning tool available in Kali Linux. It's a flexible and highly configurable tool that can be used to perform various types of scans, including TCP, UDP, ICMP, and OS detection scans. Here's an overview of how to use Unicornscan and some examples:

**Basic Syntax:**
```
unicornscan [options] <target_ip_or_range>
```
**Common Options:**

* `-h` or `--help`: Displays help and usage information.
* `-v` or `--verbose`: Increases verbosity of output.
* `-t` or `--timeout`: Sets the timeout value in seconds (default is 5 seconds).
* `-p` or `--ports`: Specifies the ports to scan (e.g., `-p 21-25` scans ports 21-25).
* `-o` or `--output`: Specifies the output file or format (e.g., `-o xml` saves output in XML format).

**Examples:**

1. **Basic TCP Scan**: Scan a single host or a range of hosts for open TCP ports:
```
unicornscan 192.168.1.100
```
or
```
unicornscan 192.168.1.100-150
```
2. **UDP Scan**: Scan a host or range of hosts for open UDP ports:
```
unicornscan -u 192.168.1.100
```
3. **ICMP Scan**: Perform an ICMP echo request scan to determine if a host is alive:
```
unicornscan -i 192.168.1.100
```
4. **OS Detection**: Attempt to identify the operating system of a target host:
```
unicornscan -O 192.168.1.100
```
5. **Port Range Scan**: Scan a range of ports on a target host:
```
unicornscan -p 21-25 192.168.1.100
```
6. **Output to XML**: Save the scan results in XML format:
```
unicornscan -o xml 192.168.1.100
```
7. **Verbose Mode**: Increase the verbosity of the output:
```
unicornscan -v 192.168.1.100
```
8. **Timeout**: Set a custom timeout value:
```
unicornscan -t 10 192.168.1.100
```
**Tips and Variations:**

* Use `-b` or `--binary` to output results in binary format.
* Use `-c` or `--csv` to output results in CSV format.
* Use `-g` or `--grep` to search for specific patterns in the output.
* Use `-r` or `--random` to randomize the order of port scans.
* Use `-s` or `--script` to execute a custom script after the scan.

Remember to use Unicornscan in a responsible and legal manner, respecting the targets and networks you're scanning. Always ensure you have the necessary permissions and comply with applicable laws and regulations.







                                                                    ALTERNATIVE
Unicornscan is a powerful and efficient network scanning tool that comes pre-installed with Kali Linux. It is designed for information gathering and is particularly useful for penetration testing. Unlike traditional scanners like Nmap, Unicornscan operates asynchronously, allowing it to perform scans more quickly and efficiently.

### Key Features of Unicornscan
- **Asynchronous Scanning**: It can send multiple packets simultaneously, making it faster than synchronous tools.
- **TCP and UDP Scanning**: Supports both TCP and UDP scans, allowing for comprehensive network analysis.
- **Banner Grabbing**: Can capture service banners for identifying running services on open ports.
- **OS and Application Identification**: Capable of identifying operating systems and applications based on responses received.
- **PCAP Logging**: Allows saving scan results in PCAP format for further analysis.
- **Custom Module Support**: Users can create and use custom modules for specific scanning needs.

### Basic Usage
To use Unicornscan, you can start with a basic TCP scan. Here’s how to perform a simple scan:

1. **Basic TCP Scan**:
   ```bash
   unicornscan -mT -Iv 192.168.0.1
   ```
   This command scans the target IP (192.168.0.1) for open TCP ports.

2. **Scanning Multiple Hosts**:
   You can scan multiple hosts by listing them in the command:
   ```bash
   unicornscan -mT -Iv 192.168.0.1 192.168.0.2
   ```

3. **Specifying Packets per Second**:
   To control the rate of packets sent, use the `-r` option:
   ```bash
   unicornscan -mT -r30 192.168.0.1
   ```
   This sends 30 packets per second to the target.

4. **UDP Scanning**:
   For scanning UDP ports, use the `-mU` option:
   ```bash
   unicornscan -mU -Iv 192.168.0.1
   ```

5. **Saving Results to a PCAP File**:
   To save the scan results, you can use the `-w` option:
   ```bash
   unicornscan -mT -w scan_results.pcap 192.168.0.1
   ```

### Advanced Features
Unicornscan also supports advanced features such as:
- **Customizing TCP Flags**: You can specify TCP flags for more tailored scans.
- **Using PCAP Filters**: Apply filters to refine the data captured during scans.
- **Verbose Output**: Use the `-v` option for more detailed output during scans.

### Conclusion
Unicornscan is a versatile tool for network scanning and can be particularly useful for security professionals looking to gather information about networked devices quickly and efficiently. Its asynchronous nature and various scanning capabilities make it a valuable addition to any penetration tester's toolkit.

---
Learn more:
1. [Unicornscan - Penetration Testing Tool in Kali Linux - GeeksforGeeks](https://www.geeksforgeeks.org/unicornscan-penetration-testing-tool-in-kali-linux/)
2. [unicornscan | Kali Linux Tools](https://www.kali.org/tools/unicornscan/)
3. [Unicornscan -- Total Guide for Beginner](https://www.kalilinux.in/2020/12/unicornscan-kali-linux.html)






   
                                                      
