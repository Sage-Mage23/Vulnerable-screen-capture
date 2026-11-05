# Vulnerable-screen-capture
CVE write-up regarding a gpu driver allowing local information disclosure via missing authorization in a kernel-mode display driver.

I'm currently waiting to hear back from the company regarding the report I submitted. If I don't receive a response or the report is rejected, I'll publish the full technical write-up.

The core vulnerability lies in a GPU driver that lacks proper privilege checks and security enforcement. This allows any process, regardless of whether it has a SYSTEM token, to access the driver's symbolic link and issue IOCTLs associated with screen capture.

As a result, an attacker can capture screenshots and record screen activity without the user's knowledge, requiring no additional privileges or elevated access. This behavior persists even with Windows security protections enabled, including HVCI (Hypervisor-Protected Code Integrity).
