Harden the kernel via various tools.
Implement Linux Security Modules and management tools.

As vulnerabilities are discovered, you may need to update Kubernetes on a regular basis. As Kubernetes, and other projects, have been rather dynamic, this leads to an important decision: update whenever a vulnerability is found (but then have disruption when the API changes and existing configurations may need to be edited and redeployed); or stay with the known working cluster (and hope the vulnerability is not exploited.)


Kernel Vulnerabilities

Seccomp

Secure computing mode (seccomp) is a mechanism which restricts access to system calls by processes

Linux Security Modules (LSM)

The Linux Security Modules (LSM) API implements hooks at all security-critical points within the kernel. A user of the framework (an LSM) can register with the API and receive callbacks from these hooks. 

Various security modules leverage LSM:

This encourages code reuse
It minimizes modifications to the kernel
It reduces changes to the kernel ABI (Application Binary Interface)
No need to modify applications.

The following LSMs have been incorporated into the mainline Linux kernel:

AppArmor: To restrict capabilities of an application.
SELinux: Implements MAC (Mandatory Access Control)


Trusted Platform Module (TPM)

TPM is a hardware feature that provides a way to store checksums:

For boot volumes, biometric data, etc.
Can be used later for comparison and authentication.

Trusted Executed Technology (TXT)
TXT is used to isolate the memory used by guest virtual machines. A guest VM could have a malicious kernel that tried to access memory owned by a host or another guest. TXT is an efficient, hardware-based method for preventing this from happening.

kernel.modules disabled
System administrators can use a one-way method to block module loading after the system has booted and all modules have been loaded. This mechanism consists in writing "1" to kernel.modules_disabled. This requires root or CAP_SYS_MODULE capabilities. No other module-related operations will be allowed from that point on.


 wget https://training.linuxfoundation.org/cm/LFS260/LFS260_V2021-03-05_SOLUTIONS.tar.xz --user=LFtraining --password=Penguin2014

    tar -xvf LFS260_V2021-03-05_SOLUTIONS.tar.xz


 sudo sh -c "useradd -m -s /bin/bash dan ; echo "dan:danpassword" | chpasswd"

sudo sh -c "useradd -m -s /bin/bash paul ; echo "paul:paulpassword" | chpasswd"



 wget https://training.linuxfoundation.org/cm/LFS260/LFS260_V2021-03-05_SOLUTIONS.tar.xz --user=LFtraining --password=Penguin2014

 cp /home/student/LFS260/SOLUTIONS/s_04/gatekeeper.yaml .

