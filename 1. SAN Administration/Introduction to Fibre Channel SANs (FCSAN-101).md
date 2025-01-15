# SAN 
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
      ![image](https://github.com/user-attachments/assets/83b6e638-07b4-4945-be6b-f1865d8e89fb)

  - Host servers attach to the local area network (LAN) and the SAN.
      ![image](https://github.com/user-attachments/assets/c47980df-a07b-4a4c-8cec-a4a4dff0a69f)

  - I Fibre Channel a port type identifies what a port is and how it will be used
  - The most common Fibre Channel port types are:
    - N_Port: Node port - A port on an HBA or storage controller that connects to a switch or director port.
    - F_Port: Fabric port - A switch or director port that is attached to an N_Port.
    - E_Port: Expansion port - A port user for inter-switch links ISLs.
      ![image](https://github.com/user-attachments/assets/da693fc9-c89e-4287-b3b7-431bae10d24a)


* World Wide Name
  - A Word Wide Name (WWN) is a globally unique address used to identify each Fibre Channel node and node port.
  - A node is a switch, HBA or Storage controller. 
  - Note: A Storage can have one or more controllers and a server can have one or more HBAs.
      ![image](https://github.com/user-attachments/assets/303d0ca3-f25e-4b5c-bb1e-38e37ad015a9)


* Zoning
  - Enables the partitioning of the devices attached to a fabric into logical groups called zones.
  - When Zonning is enabled:
    -  Devices defined in the same zone are restricted to communicate only with the devices in that zone.
    -  Devices that are not zoned are isolated from other devices in the fabric.
    -  A devices cam be member of multiple zones.
      ![image](https://github.com/user-attachments/assets/b1d4e843-0064-43e2-8afe-b88020a21058)

* Zone Membership
  - There are two ways to define a device as a member of a Zone
      - WWN
          - Both Port WWN (WWPN) and Node WWN (WWNN) are supported
      - Domain / Port
    
  ![image](https://github.com/user-attachments/assets/9ac53665-08f0-47bc-867a-9a4d9ee4d92a)

* Advanced Switch Features and Tools
  - Access Gateway (AG)
  - Trunking
  - Fabric Extension
      - Long Distance (LD) ISLs
      - Fibre Channel over IP (FCIP)
  - Fibre Channel Routing (FCR)
  - Virtual Fabrics (VF)

     ![image](https://github.com/user-attachments/assets/b9ffe2d4-aa70-480e-b185-d17b16593c4f)


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
      ![image](https://github.com/user-attachments/assets/6092ef55-13c7-4f0b-a8c3-5c7321be45ae)

  * Cascade: Switches / directors connected in series
    - Pro:
        - Lowest port count for ISLs.
        - Straightforward way to simplify switch maanagement.
        - SAN starts small, stays small and has high levels of lacality.
    - Con:
        - Availability and scalability
        - Lower performnce with more then two swithces / directors in s fabric.
    - Recommended solution for two switch or director fabrics.
      
   ![image](https://github.com/user-attachments/assets/63285251-0c6b-4b95-9e33-8fce8f99414a)


   * Ring: A variation on the Cascade topology
    - Pro:
        - Same as Cascade but with better performance and availability.
    - Con:
        - Poor scalability
    - Recommneded solution for three to four switch/director fabrics.
      ![image](https://github.com/user-attachments/assets/752f1d3f-55c6-4561-a95d-989272391a55)

  * Mesh: Connects each switch/director to every other switch/director
    - Pro:
        - Provides greator fabric resiliency than Cascade or Ring
        - Maximum of one hop to any device
    - Con:
        - Doesnot scale well
        - Lower user port availability due to increased ISL count
    - Recommneded for solution with no plans for growth and four switches per fabric.
        - Higher-port count switches and directors make mesh-based topologies more scalable.

     ![image](https://github.com/user-attachments/assets/e5ec6457-f377-4140-b3b9-27700c905035)


  * Core/Edge: Specializes the role o the switches and directors
      - Connect servers and storage to switches at the edge.
      - Connect switches at the core to the edge switches.
      - Hosts and Storage may also be attached directly to the core, depending on deisgn requirements.
      - Pro:
          - Excellent scalability, availability and perormance.
          - Addding a new Edge switch requires connections only to the Core switches, which makes this a highly scalable topology.
          - Having two Core switches makes this highly resilient topology.
      - Con:
          - High cost.
      - Recommneded for solutions with the plans fot growth and more than four swithces per fabric
          - Provides the best mix of scalabiltity, perormance and availability.
      ![image](https://github.com/user-attachments/assets/e153cce1-8901-43f4-b481-02fe71db34a7)


  * Fabric Redundancy and Resiliency
      - A dual fabric design provides the hisghest level of redundancy.
      ![image](https://github.com/user-attachments/assets/c015d918-dbfa-429f-9cf9-0df308f1c097)




      
