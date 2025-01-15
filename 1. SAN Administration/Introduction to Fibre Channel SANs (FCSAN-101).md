# SAN Context 
  ### After completing this reading, all should be able to:
  1. Understand what a SAN is
  2. Explain what a Fibre Channel Fabric is
  3. Identify the common components of a SAN
  4. Understand common Fibre Channel concepts such as port types, world wide name and Zoning.
  5. Explain the diffrent types of fabric topologies and their benefits.
  6. Identify Brocade Fibre Channel features and tools.

No prerequisets needed

## 1. Intoduction to Fibre Channel SANs

* What is SAN?
  - A storage area network or SAN is one or more purpose built networks used for storage connectivity.
  - Most SANs are built using Fibre Channel switches and directors
  - A fabric is a single dedicated strorage network within the SAN
  - A SAN consists of one or more Fabrics
    ![image](https://github.com/user-attachments/assets/3a5c958d-f64a-47f2-9da5-1c90c6029f2e)

* Standard Components of a Fibre Channel SAN
    ![image](https://github.com/user-attachments/assets/b23bca62-9cc1-4edf-a00c-f80c374ea024)

* Connectivity
  - The primary purpose of a SAN is to connect and share valuable resources.
    -  Host Servers and storage systems are attched to fabrics
--------
  - Host servers attach to the local area network (LAN) and the SAN.
--------
  - I Fibre Channel a port type identifies what a port is and how it will be used
  - The most common Fibre Channel port types are:
    - N_Port: Node port - A port on an HBA or storage controller that connects to a switch or director port.
    - F_Port: Fabric port - A switch or director port that is attached to an N_Port.
    - E_Port: Expansion port - A port user for inter-switch links ISLs.
--------

* World Wide Name
  - A Word Wide Name (WWN) is a globally unique address used to identify each Fibre Channel node and node port.
  - A node is a switch, HBA or Storage controller. 
  - Note: A Storage can have one or more controllers and a server can have one or more HBAs.

-------

* Zoning
  - Enables the partitioning of the devices attached to a fabric into logical groups called zones.
  - When Zonning is enabled:
    -  Devices defined in the same zone are restricted to communicate only with the devices in that zone.
    -  Devices that are not zoned are isolated from other devices in the fabric.
    -  A devices cam be member of multiple zones.
-------------
* Zone Membership
  - There are two ways to define a device as a member of a Zone
      - WWN
          - Both Port WWN (WWPN) and Node WWN (WWNN) are supported
      - Domain / Port
------------
* Advanced Switch Features and Tools
  - Access Gateway (AG)
  - Trunking
  - Fabric Extension
      - Long Distance (LD) ISLs
      - Fibre Channel over IP (FCIP)
  - Fibre Channel Routing (FCR)
  - Virtual Fabrics (VF)
----------

## 2. Fibre Channel Topologies
  ### SAN Fabric Topologies
  * Single switch: Simplest SAN Solution
    - Pro:
        - Locally between servers and storage
        - Wekk suited to higher port count switches
    - Con:
        - Sacalabiltity limited by switch port count
        - Not resilient and availability restricted to switch and diretor field replacable components.
    - Recommneded Soultion for Small deployments.
        - Higher-port count switches and directors make single-switch topologies possible.
--------
  * Cascade: Switches / directors connected in series
    - Pro:
        - Lowest port count for ISLs.
        - Straightforward way to simplify switch maanagement.
        - SAN starts small, stays small and has high levels of lacality.
    - Con:
        - Availability and scalability
        - Lower performnce with more then two swithces / directors in s fabric.
    - Recommended solution for two switch or director fabrics.

---------------
  * Ring: A variation on the Cascade topology
    - Pro:
        - Same as Cascade but with better performance and availability.
    - Con:
        - Poor scalability
    - Recommneded solution for three to four switch/director fabrics.
-----
  * Mesh: Connects each switch/director to every other switch/director
    - Pro:
        - Provides greator fabric resiliency than Cascade or Ring
        - Maximum of one hop to any device
    - Con:
        - Doesnot scale well
        - Lower user port availability due to increased ISL count
    - Recommneded for solution with no plans for growth and four switches per fabric.
        - Higher-port count switches and directors make mesh-based topologies more scalable.

--------------



      
