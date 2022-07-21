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
2. Netgen - Performs LVS Checks
3. CVC - Performs Circuit Validity Checks
