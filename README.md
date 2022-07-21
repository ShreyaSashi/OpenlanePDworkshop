# OpenlanePDworkshop
# Overview
OpenLANE is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, Fault, OpenSTA, TritonRoute for design exploration and optimization. The flow performs full ASIC implementation steps from RTL all the way down to GDSII
Below figure shows the OpenLane architecture
![image](https://user-images.githubusercontent.com/108127167/180239988-ab6c92be-9cde-4f63-aacf-73af1b8476fe.png)
# OpenLane Design Stages
The design stages and the tools used for the same are described below

# Synthesis
1. yosys - Performs RTL synthesis
2. abc - Performs technology mapping
3. OpenSTA - Pefroms static timing analysis on the resulting netlist to generate timing reports

# Floorplan and PDN
1. init_fp - Defines the core area for the macro as well as the rows (used for placement) and the tracks (used for routing)
2. ioplacer - Places the macro input and output ports
3. pdn - Generates the power distribution network
4. tapcell - Inserts welltap and decap cells in the floorplan

# Placement
1. RePLace - Performs global placement
2. Resizer - Performs optional optimizations on the design
3. OpenPhySyn - Performs timing optimizations on the design
4. OpenDP - Perfroms detailed placement to legalize the globally placed components

# CTS
TritonCTS - Synthesizes the clock distribution network (the clock tree)

# Routing 
1. FastRoute - Performs global routing to generate a guide file for the detailed router
2. TritonRoute - Performs detailed routing
3. SPEF-Extractor - Performs SPEF extraction

# GDSII Generation
 Magic - Streams out the final GDSII layout file from the routed def

# Checks
1. Magic - Performs DRC Checks & Antenna Checks

# OpenLane Directory Structure
The section below shows openLane Directory structure and the files present in pdk
![1](https://user-images.githubusercontent.com/108127167/180273733-2b685ef2-fe35-4141-b377-6f674f46ef4f.PNG)
![2](https://user-images.githubusercontent.com/108127167/180273781-55a57c3d-644a-4a54-b71a-58832e78bd35.PNG)
![3](https://user-images.githubusercontent.com/108127167/180273819-0163fccd-1433-4b34-a062-1784c0c7a97b.PNG)
![4](https://user-images.githubusercontent.com/108127167/180273832-c2ae0a73-e80b-4dec-8227-b756766b8739.PNG)

# Lab section
# Docker
![5](https://user-images.githubusercontent.com/108127167/180274249-0d251f4e-3af2-4f5d-8427-91a892d37da0.PNG)
![6](https://user-images.githubusercontent.com/108127167/180274371-182419ca-8858-4564-b23e-e5da7d6c07ce.PNG)
# Design prep
![7](https://user-images.githubusercontent.com/108127167/180274797-b30825d8-c72f-4f83-9730-32d8a5a6a47f.PNG)
![11](https://user-images.githubusercontent.com/108127167/180274822-db54f6f3-9b89-48b6-a2f0-09eb88eafedb.PNG)
Output of this stage
![image](https://user-images.githubusercontent.com/108127167/180275074-74ba8412-5d97-4a1c-88d4-33db7c4e4230.png)
![13](https://user-images.githubusercontent.com/108127167/180275131-aa59260e-47ca-4af3-9071-6beaf7309514.PNG)
# Synthesis
![14](https://user-images.githubusercontent.com/108127167/180275290-a6b19fdf-c6aa-4d43-a4ec-d845e86d39c1.PNG)
![15](https://user-images.githubusercontent.com/108127167/180275297-5d42f159-9038-4e41-b25a-2d3ca15b7de0.PNG)
![16](https://user-images.githubusercontent.com/108127167/180275299-743f776c-777e-40fb-9273-6e2f22d4bf25.PNG)
Synthesis result
![17](https://user-images.githubusercontent.com/108127167/180275533-fffa433a-2dda-4c4e-b39e-cf2ff6a0260f.PNG)
![18](https://user-images.githubusercontent.com/108127167/180275542-bcd1bc7c-00a7-48f6-a83d-78b240ae40f1.PNG)
Synthesis keywords
![20](https://user-images.githubusercontent.com/108127167/180275765-cf64c10f-2edb-4779-a123-6425d2dbe7a0.PNG)
# Floorplan
![21](https://user-images.githubusercontent.com/108127167/180275983-bf57cfff-6e78-47cd-9ee9-17ee7a8a01e0.PNG)
![22](https://user-images.githubusercontent.com/108127167/180275989-1484e159-9225-4170-9313-61857fee44a8.PNG)
![23](https://user-images.githubusercontent.com/108127167/180276046-924b8044-580b-425f-a182-dcbb293393de.PNG)
Floorplan output
![24](https://user-images.githubusercontent.com/108127167/180276168-badd0021-fdc2-499e-979a-b1d830ed5e9e.PNG)
Load floorplan def in Magic
![25](https://user-images.githubusercontent.com/108127167/180276316-9c4cb8d1-7c26-416a-83f0-94aef472b3d1.PNG)
![26](https://user-images.githubusercontent.com/108127167/180276323-0feea90a-3c26-45ee-9f95-08155a5c9242.PNG)
# Placement
![27](https://user-images.githubusercontent.com/108127167/180276476-347cb370-3e61-44f8-a02b-5dac439e9eba.PNG)
![28](https://user-images.githubusercontent.com/108127167/180276480-8b676716-df0e-4246-af6a-8b0693b22f5e.PNG)
Load placement def in Magic tool
![29](https://user-images.githubusercontent.com/108127167/180276645-1f6aa108-90db-4716-8255-6489b4a5a192.PNG)
![30](https://user-images.githubusercontent.com/108127167/180276652-6f30a95b-37a0-4e22-9b00-0337a0bc6fd2.PNG)
Floorplan with non uniform io 
![image](https://user-images.githubusercontent.com/108127167/180277164-535c7940-0499-4a71-bd11-6fd60086cc01.png)
![33](https://user-images.githubusercontent.com/108127167/180277085-e233576b-df62-42a0-b50e-1667bfe2a58c.PNG)

# Std Cell charecterisation
![34](https://user-images.githubusercontent.com/108127167/180277674-84351586-7780-444d-a856-cd949f1c7f1f.PNG)
![35](https://user-images.githubusercontent.com/108127167/180277675-e8a4e2e4-9f51-4f08-9563-43ed80e19d4f.PNG)
Extracting the spice netlist
![37](https://user-images.githubusercontent.com/108127167/180277966-2a5bddce-fccd-4225-afc5-744e861f4b51.PNG)
![38](https://user-images.githubusercontent.com/108127167/180277969-be1b4aca-701c-47e3-b5a6-5e7ff124f480.PNG)
![39](https://user-images.githubusercontent.com/108127167/180277971-d32d596f-63c3-4ff0-ab5f-4041fdcb28c9.PNG)
Spice netlist dumped
![41](https://user-images.githubusercontent.com/108127167/180278189-efae6ab7-95c5-42d8-a143-69ead6589962.PNG)
Corrected spice netlist
![42](https://user-images.githubusercontent.com/108127167/180278255-303e5c39-c34a-4ef5-9f9f-1c03ac513f3a.PNG)
Command to run spice on this netlist
![43](https://user-images.githubusercontent.com/108127167/180278422-af80e513-04d0-48b6-ba44-761a5062e431.PNG)
Simulation output
![44](https://user-images.githubusercontent.com/108127167/180278472-706f5a82-cf4b-4309-ac08-10dfbc40596b.PNG)
# DRC


![45](https://user-images.githubusercontent.com/108127167/180279177-fe26df9d-8a17-4128-a3fb-67be61948a63.PNG)
![46](https://user-images.githubusercontent.com/108127167/180279182-08dd62bc-53fd-486d-b87d-bd156d8969f5.PNG)
