# CASINO LFI - Dangerous Inclusion in the Casino Server

In this lab, you will analyze a seemingly simple online casino webpage, detect a local file inclusion (LFI) vulnerability, and access a hidden file containing a flag. In this lab, you will learn:

- Exploring URL parameters
- Detecting LFI vulnerabilities
- Manipulating relative paths
- Accessing internal system files
- Reading flags from the web server

<how-to-start>
   
## 🌱 How to Start This Lab

Follow these instructions to get started:

1. **Download the virtual machine** from this [link](https://storage.googleapis.com/cybersecurity-machines/casino-lab.ova).
2. **Import the machine** into your preferred virtualization manager (VirtualBox, VMware, etc.).
3. Once the machine is running, you can start the lab!

</how-to-start>

## 📄 Instructions

You are facing the website of a fictional casino called **Casino Royale**. Your task is to analyze how the page is built and discover if there is any vulnerability in the use of paths and files.

1. **Discover the IP address of the CASINO LFI machine.**: The machine is connected to the same network as you, but its IP has not been provided. Use tools like `nmap`, `netdiscover`, or `arp-scan` to scan the network.

2. **Access the website hosted on the server.**
   - Open your browser and visit the assigned IP.
   - Observe the content displayed with:
     ```
     ?page=home
     ?page=about
     ```

3. **Explore the vulnerable parameter.**: Can you modify the value of the `page` parameter?

4. **Extract the flag's content.**

**Remember:** not every included file was meant to be seen.

Happy hacking!

