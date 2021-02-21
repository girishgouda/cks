Conatiner Security

Aqua - Container life cycle Security - Triviy 
Notary - Publish data and verifying the content using keys such as TLS to ensure the data is changed
Harbor - Secure Registry and manage artifcats for cloud native platforms and Docker


Grafeas - stores structured metadata about an object in a flexible and easy to query manner

Grafeas - Container resitry vulnerabilty scanning
kritis - Binary Authorization

Container Runtime

gVisor and Kata are the most common in use.
gVisor - Sanbox isolation project for containers - lightweight and secure

gVisor is a Go-written sandbox often used along with rule-based execution tools such as SELinux or seccomp. It provides an independent kernel between the host and the containerized application.

It acts as a kernel in between the containerized application and the host kernel. It does this through various mechanisms to support syscall limits, file system proxying, and network access. These mechanisms are a paravirtualization providing a virtual-machine like level of isolation, without the fixed resource cost of each virtual machine.

RunTimeClass

apiVersion: node.k8s.io/v1beta1
kind: RuntimeClass
metadata:
  name: gvisor
handler: runsc

Pod Spec

....
spec:
  runtimeClassName: gvisor   #<<--This must match the name of the runtime above
  containers:
....

Kata
Unlike traditional containers which share a host kernel and use namespaces to keep isolated, Kata leverages hardware virtualization, to provide per-container kernels. This provides an extra layer of isolation for workload and security concerns.

Trusted Packages
Projects such as The Update Framework (TUF) are designed to provide a verifiable record of the state of the software to avoid attacks which provide older or unapproved files. TUF is a graduated project of CNCF.

Another CNCF project, Notary, is based off of TUF, which allows for verifying software across the internet, and mitigating several possible compromises.

Centralize Tools

 Open Policy Agent (OPA)

 not startswith(image, "linux.com/")