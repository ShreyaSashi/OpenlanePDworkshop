# OpenlanePDworkshop<br />
# Overview<br />
OpenLANE is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, Fault, OpenSTA, TritonRoute for design exploration and optimization. The flow performs full ASIC implementation steps from RTL all the way down to GDSII<br />
Below figure shows the OpenLane architecture<br />
![image](https://user-images.githubusercontent.com/108127167/180239988-ab6c92be-9cde-4f63-aacf-73af1b8476fe.png)<br />
# OpenLane Design Stages<br />
The design stages and the tools used for the same are described below<br />

# Synthesis<br />
1. yosys - Performs RTL synthesis<br />
2. abc - Performs technology mapping<br />
3. OpenSTA - Pefroms static timing analysis on the resulting netlist to generate timing reports<br />

# Floorplan and PDN<br />
1. init_fp - Defines the core area for the macro as well as the rows (used for placement) and the tracks (used for routing)<br />
2. ioplacer - Places the macro input and output ports<br />
3. pdn - Generates the power distribution network<br />
4. tapcell - Inserts welltap and decap cells in the floorplan<br />

# Placement<br />
1. RePLace - Performs global placement<br />
2. Resizer - Performs optional optimizations on the design<br />
3. OpenPhySyn - Performs timing optimizations on the design<br />
4. OpenDP - Perfroms detailed placement to legalize the globally placed components<br />

# CTS<br />
TritonCTS - Synthesizes the clock distribution network (the clock tree)<br />

# Routing <br />
1. FastRoute - Performs global routing to generate a guide file for the detailed router<br />
2. TritonRoute - Performs detailed routing<br />
3. SPEF-Extractor - Performs SPEF extraction<br />

# GDSII Generation<br />
 Magic - Streams out the final GDSII layout file from the routed def<br />

# Checks<br />
1. Magic - Performs DRC Checks & Antenna Checks<br />

# OpenLane Directory Structure<br />
The section below shows openLane Directory structure and the files present in pdk<br />
![1](https://user-images.githubusercontent.com/108127167/180273733-2b685ef2-fe35-4141-b377-6f674f46ef4f.PNG)<br />
![2](https://user-images.githubusercontent.com/108127167/180273781-55a57c3d-644a-4a54-b71a-58832e78bd35.PNG)<br />
![3](https://user-images.githubusercontent.com/108127167/180273819-0163fccd-1433-4b34-a062-1784c0c7a97b.PNG)<br />
![4](https://user-images.githubusercontent.com/108127167/180273832-c2ae0a73-e80b-4dec-8227-b756766b8739.PNG)<br />

# Lab section<br />
# Docker<br />
![5](https://user-images.githubusercontent.com/108127167/180274249-0d251f4e-3af2-4f5d-8427-91a892d37da0.PNG)<br />
![6](https://user-images.githubusercontent.com/108127167/180274371-182419ca-8858-4564-b23e-e5da7d6c07ce.PNG)<br />

# Design prep<br />
![7](https://user-images.githubusercontent.com/108127167/180274797-b30825d8-c72f-4f83-9730-32d8a5a6a47f.PNG)<br />
![11](https://user-images.githubusercontent.com/108127167/180274822-db54f6f3-9b89-48b6-a2f0-09eb88eafedb.PNG)<br />

**Output of this stage**<br />
![image](https://user-images.githubusercontent.com/108127167/180275074-74ba8412-5d97-4a1c-88d4-33db7c4e4230.png)<br />
![13](https://user-images.githubusercontent.com/108127167/180275131-aa59260e-47ca-4af3-9071-6beaf7309514.PNG)<br />

# Synthesis<br />
![14](https://user-images.githubusercontent.com/108127167/180275290-a6b19fdf-c6aa-4d43-a4ec-d845e86d39c1.PNG)<br />
![15](https://user-images.githubusercontent.com/108127167/180275297-5d42f159-9038-4e41-b25a-2d3ca15b7de0.PNG)<br />
![16](https://user-images.githubusercontent.com/108127167/180275299-743f776c-777e-40fb-9273-6e2f22d4bf25.PNG)<br />

**Synthesis result**<br />
![17](https://user-images.githubusercontent.com/108127167/180275533-fffa433a-2dda-4c4e-b39e-cf2ff6a0260f.PNG)<br />
![18](https://user-images.githubusercontent.com/108127167/180275542-bcd1bc7c-00a7-48f6-a83d-78b240ae40f1.PNG)<br />

**Synthesis keywords**<br />
![20](https://user-images.githubusercontent.com/108127167/180275765-cf64c10f-2edb-4779-a123-6425d2dbe7a0.PNG)<br />

# Floorplan<br />
![21](https://user-images.githubusercontent.com/108127167/180275983-bf57cfff-6e78-47cd-9ee9-17ee7a8a01e0.PNG)<br />
![22](https://user-images.githubusercontent.com/108127167/180275989-1484e159-9225-4170-9313-61857fee44a8.PNG)<br />
![23](https://user-images.githubusercontent.com/108127167/180276046-924b8044-580b-425f-a182-dcbb293393de.PNG)<br />

**Floorplan output**<br />
![24](https://user-images.githubusercontent.com/108127167/180276168-badd0021-fdc2-499e-979a-b1d830ed5e9e.PNG)<br />

**Load floorplan def in Magic**<br />
![25](https://user-images.githubusercontent.com/108127167/180276316-9c4cb8d1-7c26-416a-83f0-94aef472b3d1.PNG)<br />
![26](https://user-images.githubusercontent.com/108127167/180276323-0feea90a-3c26-45ee-9f95-08155a5c9242.PNG)<br />


# Placement<br />
![27](https://user-images.githubusercontent.com/108127167/180276476-347cb370-3e61-44f8-a02b-5dac439e9eba.PNG)<br />
![28](https://user-images.githubusercontent.com/108127167/180276480-8b676716-df0e-4246-af6a-8b0693b22f5e.PNG)<br />

**Load placement def in Magic tool**<br />
![29](https://user-images.githubusercontent.com/108127167/180276645-1f6aa108-90db-4716-8255-6489b4a5a192.PNG)<br />
![30](https://user-images.githubusercontent.com/108127167/180276652-6f30a95b-37a0-4e22-9b00-0337a0bc6fd2.PNG)<br />

Floorplan with non uniform io <br />
![image](https://user-images.githubusercontent.com/108127167/180277164-535c7940-0499-4a71-bd11-6fd60086cc01.png)<br />
![33](https://user-images.githubusercontent.com/108127167/180277085-e233576b-df62-42a0-b50e-1667bfe2a58c.PNG)<br />


# Std Cell charecterisation<br />
![34](https://user-images.githubusercontent.com/108127167/180277674-84351586-7780-444d-a856-cd949f1c7f1f.PNG)<br />
![35](https://user-images.githubusercontent.com/108127167/180277675-e8a4e2e4-9f51-4f08-9563-43ed80e19d4f.PNG)<br />

**Extracting the spice netlist**<br />
![37](https://user-images.githubusercontent.com/108127167/180277966-2a5bddce-fccd-4225-afc5-744e861f4b51.PNG)<br />
![38](https://user-images.githubusercontent.com/108127167/180277969-be1b4aca-701c-47e3-b5a6-5e7ff124f480.PNG)<br />
![39](https://user-images.githubusercontent.com/108127167/180277971-d32d596f-63c3-4ff0-ab5f-4041fdcb28c9.PNG)<br />

**Spice netlist dumped**<br />
![41](https://user-images.githubusercontent.com/108127167/180278189-efae6ab7-95c5-42d8-a143-69ead6589962.PNG)<br />

**Corrected spice netlist**<br />
![42](https://user-images.githubusercontent.com/108127167/180278255-303e5c39-c34a-4ef5-9f9f-1c03ac513f3a.PNG)<br />

**Command to run spice on this netlist**<br />
![43](https://user-images.githubusercontent.com/108127167/180278422-af80e513-04d0-48b6-ba44-761a5062e431.PNG)<br />

**Transient Analysis waveform**<br />
![44](https://user-images.githubusercontent.com/108127167/180278472-706f5a82-cf4b-4309-ac08-10dfbc40596b.PNG)<br />

**Adding Lef port and type**<br />
![54_adding_port_type](https://user-images.githubusercontent.com/108127167/180359051-16ec11bb-6174-473d-806b-9ecd605a41ac.PNG)<br />

**Created Lef**<br />
![55_created_lef](https://user-images.githubusercontent.com/108127167/180359409-5b5698a3-50f7-4ba2-a8b7-8e63949d5635.PNG)<br />


# Including Created Std Cell in OpenLane<br />

We can start OpenLane and do design prep step. After we can add the std cell lef which was created in the previous stage using the command below<br />
![image](https://user-images.githubusercontent.com/108127167/180361068-120cc31a-4be7-4a42-a034-5e2de18291a8.png)<br />

After this we can synthesise the design and confirm whether the Lef was included<br />
![56_included_stdcell_lef](https://user-images.githubusercontent.com/108127167/180361484-1e8f76b1-ab2d-4ab7-8dc6-05bf4049aa6f.PNG)<br />

**Synthesis result**<br />
There are some slack violation after synthesis as shown below<br />
![57_result_after_synthesis](https://user-images.githubusercontent.com/108127167/180361590-1cbbbf19-9fb8-4925-a1ca-eb99d400c52d.PNG)<br />

**Synthesis settings**<br />
We can try adjusting the following synthesis settings to improve the slack. But this may affect the area<br />
![image](https://user-images.githubusercontent.com/108127167/180361879-462cdfd7-ca38-469b-a1ca-3f3ace008443.png)<br />
![59_synthesis_settings](https://user-images.githubusercontent.com/108127167/180361920-95a06e0d-1166-4e34-877e-f7dfd2d46119.PNG)<br />

The synthesis result shows improvement in slack, but Area increased from 147712.9184 to 196832.528<br />
![60_delay_reduced_area_increased](https://user-images.githubusercontent.com/108127167/180362835-9227d976-7b05-4452-8e17-95c52cd343ee.PNG)<br />

The image below shows the custom std cell placed in the design<br />
![62_stdcell_placed_in_design](https://user-images.githubusercontent.com/108127167/180362895-22ab96e7-065d-43ae-9342-6ac606956427.PNG)<br />

# CTS<br />
After running floorplan and standard cell placement in OpenLANE we can insert clock tree for sequential elements in our design. The main concerns with clock tree generation are<br />

Clock skew - Difference in arrival times of the clock for sequential elements across the design<br />
Delta delay - Skew introduced through capacitive coupling of the clock tree nets<br />

To run clock tree synthesis (CTS) in OpenLANE:<br />
![65_run_cts](https://user-images.githubusercontent.com/108127167/180363435-aa4ba730-5799-4725-8434-7f54a5a5ed62.PNG)<br />

The verilog netlist post CTS is saved in the results/synthesis area<br />
![66_cts_output](https://user-images.githubusercontent.com/108127167/180364684-15cdad58-1115-416e-9589-efa4e6a2f6d0.PNG)<br />

**Post CTS STA Analysis**<br />
OpenLANE has the OpenROAD application which inturn has OpenSTA integrated into its flow. Therefore, we can perform STA analysis from within OpenLANE by invoking OpenROAD.<br />
To invoke OpenROAD from OpenLANE we can use openroad command. After that we need to read the Lef/Def files:<br />
![69_openroad_read_lef_def](https://user-images.githubusercontent.com/108127167/180365020-4abd3256-7701-4828-a32c-59bbedd1e3ff.PNG)<br />

We need to create a db and read the liberty, post cts verilog and sdc files<br />
![70_](https://user-images.githubusercontent.com/108127167/180365216-5a2d67d6-9089-4fa5-9cb6-a614ae92b112.PNG)<br />

The report checks step shows that hold and setup time are met for this design<br />
![71_hold_time_met](https://user-images.githubusercontent.com/108127167/180365393-47a2fca9-2e79-47c9-9fb0-2b8779f19bf5.PNG)<br />
![72_setup_time_met](https://user-images.githubusercontent.com/108127167/180365481-fc03fb89-a188-4264-95ef-31ba209858c3.PNG)<br />

We can modify the clock buffers used in CTS as shown below and run cts again to understand the impact<br />
![73_run_cts_after_modifying_clkbuf_list](https://user-images.githubusercontent.com/108127167/180365696-ac540bd4-c0b6-4b09-a213-6f006c3bb216.PNG)<br />

# PDN Generation<br />

Following command can be used to generate Power distribution network(PDN) in OpenLane<br />
![77_PDN_creation](https://user-images.githubusercontent.com/108127167/180365902-ac4842ee-8717-4900-bbbf-28ff1f9ae250.PNG)<br />

PDN Log shows whych layers are used for std cell grid and macro grid. Note that the pitch of std cell rail indicates the height of std cells<br />
![78_PDN_log](https://user-images.githubusercontent.com/108127167/180365939-038504de-a66f-441b-8ba4-333d0c5f5163.PNG)<br />

# Routing<br />

OpenLANE uses TritonRoute as the routing engine for physical implementations of designs. Routing consists of two stages:<br />

1. Global Routing - Routing guides are generated for interconnects on our netlist defining what layers, and where on the chip each of the nets will be reputed<br />
2. Detailed Routing - Metal traces are iteratively laid across the routing guides to physically implement the routing guides<br />

The command run_routing is used for routing in OpenLane. Detailed routing goes through various level of optimization till all the violations are cleared<br />
![79_detail_route](https://user-images.githubusercontent.com/108127167/180366557-219fa8c3-3e87-4e42-941c-3749bf6023dd.PNG)<br />
![81_optimised_routing_wo_violation](https://user-images.githubusercontent.com/108127167/180366606-79e5e079-e81d-4fcb-a665-3e6ae21b3149.PNG)<br />
![82_routing_complete](https://user-images.githubusercontent.com/108127167/180367012-23e2e868-792d-407d-97b8-7495bef62802.PNG)<br />


# SPEF Extrtaction<br />
The interconnect parasitics can be extracted after routing and it will be saved in the SPEF file. SPEF file is required for post route STA analysis.<br /> 
Current version of OpenLane has Spef Extractor integrated with the routing step. Hence we are able to get the Spef file along with the routed def as part of routing output<br />
![83_routing_output](https://user-images.githubusercontent.com/108127167/180367843-b04abd96-bc5a-4bdc-8e7f-0dfe7facd8ad.PNG)<br />

**Spef file**<br />
![84_spef_from_routing](https://user-images.githubusercontent.com/108127167/180375912-1bc016a2-c009-4067-8c16-3a76a9e42eb2.PNG)<br />


# DRC<br />
![45](https://user-images.githubusercontent.com/108127167/180279177-fe26df9d-8a17-4128-a3fb-67be61948a63.PNG)<br />
![46](https://user-images.githubusercontent.com/108127167/180279182-08dd62bc-53fd-486d-b87d-bd156d8969f5.PNG)<br />

**Metal3 DRC**<br />
![48_cif see VIA2](https://user-images.githubusercontent.com/108127167/180357277-d228bac1-c8a6-4693-b244-7f2ea79f66db.PNG)<br />
Measuring the edge distance after adding VIA2<br />
![49_get_edge_distance](https://user-images.githubusercontent.com/108127167/180357023-f6b0d902-1214-4b3f-958b-ce6aa280b37c.PNG)<br />

**Polyres DRC**<br />
![50_polyres](https://user-images.githubusercontent.com/108127167/180357391-5f8e94f7-67e4-4f6d-b916-4caf1fd0af0e.PNG)<br />
poly.9 rule<br />
![image](https://user-images.githubusercontent.com/108127167/180357673-06da5c3d-14ce-4302-bdf6-d5fb9734edb6.png)<br />
Added missing rules in DRC file for poly.9 and run DRC check after loading new rule file<br />
![51_edited_drc_rule](https://user-images.githubusercontent.com/108127167/180357436-c0b3cd90-ec7a-42c3-be7a-07b148ec7270.PNG)<br />
![52_techload_and_drc_recheck](https://user-images.githubusercontent.com/108127167/180357809-46bf7bd7-40dd-4dc6-bbeb-5ceb169dbcce.PNG)<br />

**Nwell DRC**<br />
Image shows nwell_missing and dnwell_shrink<br />
![53_nwell_drc](https://user-images.githubusercontent.com/108127167/180357944-ee1dc27f-9ab4-4fc4-a9b2-26cd9c0a4666.PNG)<br />



