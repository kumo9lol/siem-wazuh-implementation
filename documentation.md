# Wazuh SIEM Setup Documentation

## Virtual Machine Specifications

### Wazuh-SIEM1 (Ubuntu Server)
- **Virtualization**: Oracle VirtualBox
- **OS**: Ubuntu 22.04 LTS (64-bit)
- **RAM**: 4096 MB (4GB)
- **Storage**: 50.00 GB
- **Network**: Bridged adapter
- **Graphics**: 128 MB VRAM, VMSVGA controller
- **Boot Order**: Hard Disk, Optical, Floppy

### WindowsAgent001 (Windows 11 Agent)
- **Virtualization**: Oracle VirtualBox
- **OS**: Windows 11 (64-bit)
- **RAM**: 4094 MB (~4GB)
- **Storage**: 50.30 GB
- **Network**: Bridged adapter
- **Secure Boot**: Enabled
- **TPM**: Enabled
- **Boot Media**: Windows 11 ISO attached
- **Graphics**: 128 MB VRAM, VBoxSVGA controller

## Installation Timeline

1. **VM Creation**: Set up both VMs in VirtualBox with bridged networking
2. **Ubuntu Setup**: Installed Ubuntu on Wazuh-SIEM1
3. **Wazuh Installation**: 
   - Installed curl: `apt install curl`
   - Downloaded and ran Wazuh installer
   - Noted dashboard credentials
4. **Windows Setup**: Installed Windows 11 on WindowsAgent001
5. **Agent Deployment**: 
   - Downloaded Wazuh agent MSI
   - Installed with manager IP 192.168.1.17
   - Started Wazuh service
6. **Verification**: Confirmed agent appears in dashboard

## Key Configuration Details

### Server Configuration:
- **Wazuh Version**: 4.14
- **IP Address**: 192.168.1.17
- **Dashboard Access**: HTTPS on port 443
- **Default Credentials**: admin / JRxQHR6Q?PbJYz5JU1qgsCE+Sv10V426

### Agent Configuration:
- **Agent Version**: 4.14.1
- **Manager IP**: 192.168.1.17
- **Agent Name**: WindowsAgent001
- **Installation Method**: Silent MSI installation

## Results & Verification
- ✅ Both VMs running successfully
- ✅ Wazuh server components installed and running
- ✅ Windows agent registered with server
- ✅ Alerts being generated (116 medium, 122 low severity)
- ✅ Active monitoring established between VMs

## Network Setup Success
- Bridged networking allows same-subnet communication
- No firewall issues between VMs
- Agent can reach manager on port 1514
- Dashboard accessible from host machine
