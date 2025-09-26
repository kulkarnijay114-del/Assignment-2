 On Linux (UFW)
1. Open firewall configuration tool
sudo ufw status
2. List current firewall rules
sudo ufw status numbered
3. Add a rule to block inbound traffic on a specific port (e.g., Telnet on port 23)
sudo ufw deny 23/tcp
4. Test the rule
Try to connect:
telnet localhost 23
It should be blocked.
5. Add a rule to allow SSH (port 22)
sudo ufw allow 22/tcp
6. Remove the test block rule (restore original state)
sudo ufw delete deny 23/tcp
7. Document commands
•	ufw status
•	ufw deny 23/tcp
•	ufw allow 22/tcp
•	ufw delete deny 23/tcp
8. Summary
UFW filters traffic based on rules that allow or deny connections. When a rule blocks a port, traffic to that port is dropped. Allowed ports (like SSH) remain open for connections.
 On Windows (Windows Firewall)
1. Open firewall tool
•	Press Win + R → wf.msc
•	Or use Control Panel → Windows Defender Firewall → Advanced Settings
2. List current firewall rules
•	Go to Inbound Rules and Outbound Rules.
3. Add a rule to block inbound traffic (e.g., Telnet on port 23)
•	Inbound Rules → New Rule → Port → TCP → Specific local port: 23 → Block the connection
4. Test the rule
•	Use telnet localhost 23 (will fail).
5. Add a rule to allow SSH (port 22)
•	Inbound Rule → New Rule → Port → TCP → Specific local port: 22 → Allow the connection
6. Remove the block rule
•	Right-click the Telnet rule → Delete.
7. Document steps
•	Used GUI: wf.msc → Inbound Rule → New Rule
•	Blocked 23, allowed 22, tested, then removed rule.
8. Summary
Windows Firewall filters traffic by applying inbound/outbound rules. Block rules drop traffic, while allow rules permit it.
