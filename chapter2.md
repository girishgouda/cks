Assessment - Securing the high value cost assets
Prevention - Control to protect assets
Detection - monitoring the assets
Reaction - measure to prevent vulnerabilities and risk - increse/decrease the confidence of the customer

Types of attacks
Active - compromises integrity and availability - DDOS,Spoofing,port scanning,Idle scan
passive - compromises confidentiality - Wiretapping - tcpdump and wireshark

4cs of security 
code
container - code - vulnerability scanning + image signing + No elevated privileges
cluster - kuberentes - 
    cluster state(etcd) , auth/authz 
    networking - only required ports
    kubelet and kube proxy - have access to control plane and should not be compromised.
cloud - CIS benchmarks,  High Value Asset Protection - non profit 
    kube-bench - vulnerabilties - aqua sec
    non-container specific security tools (SELinux, Kerberos, SAML, etc.) 