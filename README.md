# ****VSD-WORKSHOP****
This repository presents the information about the 5 day workshop conducted by VLSI system design. The workshop is based on Advanced Physical Design using OpenLANE/SOC.The schedule is given below followed by detailed account:
(Image Courtesy: Google) 
<p align="center">
<img src="https://github.com/shrutimary15/VSD-workshop/blob/main/photo_2021-01-23_19-54-03.jpg" 
alt="alt text"  >
<p/>
<br/>

# **TABLE OF CONTENTS**

  #**1. BASICS OF OPEN SOURCE EDA, OPENLANE AND SKY 130 PDK**
  * Introduction to QFN 48 package,die,core and IPs
  * SOC design using OpenLANE
  * Simplified ASIC design
  * EDA tools
  * Lab: Import package of OpenLANE and run synthesis
  
  #**2. IDEA OF FLOORPLAN AND PLACEMENT**
  * Utilization factor and aspect ratio, floor planning and preplaced cells, decoupling capacitors, power planning, pin placement
  * Library binding and placement
  * Cell Design Flow
  * Characterization flow
  
  #**3. DESIGN AND CHARACTERISTICS ONE LIBRARY CELL USING MAGIC AND NGSPICE**
  * ngspice simulation
  * 16 Mask CMOS fabrication
  * Sky130 tech file labs
  
  #**4. PRELAYOUT TIMING ANALYSIS AND IMPORTANCE OF GOOD CLOCK**
  * Timing modelling using delay tables
  * Clock tree synthesis
  * Timing analysis with real and ideal clocks
  
  #**5. FINAL STEP**
  * Routing and Design Rule Check
  * Power distribution network 
  * Triton Route Features
  
  #**6. REFERENCE**
  
  #ACKNOWLEDGEMENT
  
  
  
  # DAY 1:
 [Theory]
 
  OPENLANE : OpenLANE is a open source VLSI flow from RTL to GDSII built across open source tools such as OPENROAD, Yosys, Magic, Fault, etc.
  
  SKY130A: The SkyWater Open Source PDK is a collaboration between Google and SkyWater Technology Foundry to provide a fully open source Process Design Kit.
  
  The process begins with synthesis then followed by floor planning, power planning, placement, routing and static timing analysis. The figure below shows the flow diagram of     complete process.(Image Courtesy: Google)
  ![openlane flow 1](https://user-images.githubusercontent.com/77826778/105610075-7fe30880-5dd3-11eb-8927-1b4b084010de.png)
  Tools used in openlane are-
   *Yosys - Performs RTL synthesis
   *abc- Performs technology mapping
   *OpenSTA- performs static timing analysis
   *Fast Route- Performs global routing
   *TritonRoute- Performs detailed routing
   *Magic- Streams out the layout of GDSII
  
  [Lab Exercise]
  
 1. Invoking OpenLANE: Picorv32a design can be synthesized using openLANE. OpenLANE can be invoked in interactive mode by using the command ```./flow.tcl -interactive```.  The package can be included by using command ```package require openlane 0.9```. The design is prepared using the command ```prep -design picorv32a```. To edit any parameter in config.tcl ```set env(PARAMETER_NAME) parameter_value``` command can be used. Use -overwrite to reflect these changes in design.
 
![Capture3](https://user-images.githubusercontent.com/77826778/105609006-5d99bc80-5dcc-11eb-9915-9001fb5c6189.PNG)


 2. Running Synthesis: This is done using the command ```run_synthesis```
 
  ![Capture2](https://user-images.githubusercontent.com/77826778/105607225-9e410800-5dc3-11eb-9516-fe645dad0811.PNG)
  
  # DAY 2:
  
  [Lab Exercise]
  
  1. Running floorplan: This is done using the command ```run_floorplan```
  
  ![Capture5](https://user-images.githubusercontent.com/77826778/105608789-2676db80-5dcb-11eb-9fa6-a9d24774f71d.PNG)
  
  2. Running placement: This is done using the command ```run_placement```
  
  ![Capture7](https://user-images.githubusercontent.com/77826778/105609360-cd10ab80-5dce-11eb-8f66-cf04798b1279.PNG)
  
 
