---
sidebar_position: 1
keywords:
  - Harvester
  - harvester
  - Rancher
  - rancher
  - ISO Installation
Description: To get the Harvester ISO, download it from the Github releases. During the installation you can either choose to form a new cluster, or join the node to an existing cluster.
---

# ISO Installation

To get the Harvester ISO image, download it from the [Github releases](https://github.com/harvester/harvester/releases) page.

During the installation you can either choose to form a new cluster, or join the node to an existing cluster.

Note: This [video](https://youtu.be/X0VIGZ_lExQ) shows a quick overview of the ISO installation.

<div class="text-center">
<iframe width="950" height="475" src="https://www.youtube.com/embed/X0VIGZ_lExQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

1. Mount the Harvester ISO disk and boot the server by selecting the `Harvester Installer` option.
   ![iso-install.png](./assets/iso-install.png)
1. Choose the installation mode by either creating a new Harvester cluster, or by joining an existing one.
1. Choose the installation device on which the Harvester cluster will be installed
      - Note: By default, Harvester uses [GPT](https://en.wikipedia.org/wiki/GUID_Partition_Table) partitioning schema for both UEFI and BIOS. If you use the BIOS boot, then you will have the option to select [MBR](https://en.wikipedia.org/wiki/Master_boot_record).
   ![iso-install-disk.png](./assets/iso-install-disk.png)
1. Configure the hostname and select the network interface for the management network. By default, Harvester will create a bonded NIC named `harvester-mgmt`, and the IP address can either be configured via DHCP or a static assigned a static one.
   ![iso-installed.png](./assets/iso-nic-config.gif)
1. (Optional) Configure the DNS servers. Use commas as a delimiter.
1. Configure the `Virtual IP` which you can use to access the cluster or join other nodes to the cluster <small>(Note: If your IP address is configured via DHCP, you will need to configure static MAC-to-IP address mapping on your DHCP server in order to have a persistent Virtual IP)</small>.
1. Configure the `cluster token`. This token will be used for adding other nodes to the cluster.
1. Configure the login password of the host. The default SSH user is `rancher`.
1. (Optional) Configure the NTP Servers of the node. This defaults to `0.suse.pool.ntp.org`.
1. (Optional) If you need to use an HTTP proxy to access the outside world, enter the proxy URL address here. Otherwise, leave this blank.
1. (Optional) You can choose to import SSH keys from a remote server URL. Your GitHub public keys can be used with `https://github.com/<username>.keys`.
1. (Optional) If you need to customize the host with a [Harvester configuration](./harvester-configuration.md) file, enter the HTTP URL here.
1. After confirming the installation options, Harvester will be installed to your host. The installation may take a few minutes to be complete.
1. Once the installation is complete, it will restart the host. After the restart, the Harvester console containing the management URL and status will be displayed. You can Use `F12` to switch between the Harvester console and the Shell.
1. The default URL of the web interface is `https://your-virtual-ip`.
   ![iso-installed.png](./assets/iso-installed.png)
1. You will be prompted to set the password for the default `admin` user when logging in for the first time.
   ![first-login.png](./assets/first-time-login.png)
