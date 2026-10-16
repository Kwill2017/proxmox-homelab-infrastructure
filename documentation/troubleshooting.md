# Homelab Troubleshooting & Incident Documentation

## Incident 1: NAS Connectivity and SMB/CIFS Mount Failure

### Problem
The Ubuntu Server virtual machine intermittently lost access to shared storage hosted on a TerraMaster NAS. This disrupted applications that relied on mounted network directories.

### Environment
- Proxmox VE hypervisor
- Ubuntu Server virtual machine
- TerraMaster NAS
- SMB/CIFS network file sharing
- Docker containerized applications

### Troubleshooting Process
1. Verified network connectivity between Ubuntu Server and the NAS using `ping`.
2. Reviewed mounted filesystems using `mount` and `df -h`.
3. Inspected the `/etc/fstab` configuration for the SMB/CIFS share.
4. Investigated mount failures and unresponsive filesystem operations.
5. Unmounted and remounted the NAS share, validating access to the storage directories.
6. Reviewed mount configuration and permissions to improve reliability.

### Resolution
Restored access to the NAS share and configured persistent mounting to support application storage after system restarts.

### Skills Demonstrated
- Linux troubleshooting
- TCP/IP connectivity testing
- SMB/CIFS administration
- Filesystem management
- Root cause investigation

---

## Incident 2: Ubuntu Server Storage Capacity

### Problem
Application data and incomplete downloads consumed significant disk space on the Ubuntu Server virtual machine, reducing available storage.

### Troubleshooting Process
1. Checked disk utilization with `df -h`.
2. Identified directories consuming storage.
3. Expanded the virtual machine disk allocation through Proxmox.
4. Extended the Linux partition and filesystem.
5. Relocated temporary application download data to a dedicated directory.
6. Verified the updated storage capacity and container volume mappings.

### Resolution
Expanded available virtual machine storage and reorganized application data to reduce storage pressure.

### Skills Demonstrated
- Virtual disk administration
- Linux filesystem management
- Storage capacity planning
- Docker volume configuration

---

## Incident 3: Docker Container and VPN Connectivity

### Problem
Containerized applications experienced connectivity interruptions associated with VPN health-check failures.

### Troubleshooting Process
1. Reviewed container status using `docker ps`.
2. Examined application and VPN container logs using `docker logs`.
3. Investigated WireGuard configuration and connectivity failures.
4. Updated the VPN configuration and restarted affected services.
5. Verified container health and outbound network connectivity.

### Resolution
Restored VPN connectivity and confirmed that affected containers resumed normal operation.

### Skills Demonstrated
- Docker troubleshooting
- VPN fundamentals
- Log analysis
- Linux networking
- Service recovery
