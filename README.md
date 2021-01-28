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
  
 1. Invoking OpenLANE: Picorv32a design can be synthesized using openLANE. OpenLANE can be invoked in interactive mode by using the command ```./flow.tcl -interactive```.  The       package can be included by using command ```package require openlane 0.9```. The design is prepared using the command ```prep -design picorv32a```. To edit any parameter in     config.tcl ```set env(PARAMETER_NAME) parameter_value``` command can be used. Use -overwrite to reflect these changes in design.
 
      ![Capture3](https://user-images.githubusercontent.com/77826778/105609006-5d99bc80-5dcc-11eb-9915-9001fb5c6189.PNG)


 2. Running Synthesis: This is done using the command ```run_synthesis```
 
      ![Capture2](https://user-images.githubusercontent.com/77826778/105607225-9e410800-5dc3-11eb-9516-fe645dad0811.PNG)
  
  # DAY 2:
  [Theory]
   
   Floorplanning is the planning of placement of IO pads and macros as well as power and ground structure. It is an art of using optimum area and obtaining high performance.
   The floorplan is displaced in magic window.      
    
    
  [Lab Exercise]
  
  1. Running floorplan: This is done using the command ```run_floorplan```.
     Some basic command to use in magic 
           
         s – select
         v — fit layout
         After selecting a layer, typing `what` in tkcon 2.3 main window gives the description of the layer.
  
     ![Capture5](https://user-images.githubusercontent.com/77826778/105608789-2676db80-5dcb-11eb-9fa6-a9d24774f71d.PNG)
  
  2. Running placement: This is done using the command ```run_placement```
  
     ![Capture7](https://user-images.githubusercontent.com/77826778/105609360-cd10ab80-5dce-11eb-8f66-cf04798b1279.PNG)
  
  # DAY 3:
  [Theory]
   
   16 MASK CMOS PREPARATION-
   Following are the steps in CMOS preparation-
   
    Selecting a substrate.
    Creating active region for transistors
    N-Well and P-Well formation
    Formation of ‘gate'
    Lightly doped drain(LDD) formation
    Source and drain formation
    Steps to form contacts and interconnects(local)
    Higher level metal formation
    
    
   [Lab Excercise]
   
   Layout tool (Magic) gives the display as shown below. The layout shown below is of inverter.
   ![Capture7](https://user-images.githubusercontent.com/77826778/106092070-9979ac80-6153-11eb-8f37-c66d251d6ee6.PNG)
   
   
   The layout can be analysed using spice tool by giving the following commands in tkcon 2.3 main window.
   ![Capture13](https://user-images.githubusercontent.com/77826778/106092274-f5443580-6153-11eb-9401-ce0d9e8390dd.PNG)
   
   The **config.tcl** file is modified as shown below. Modification can be done by-
     
    i-to insert
    esc-to save
    :wq!-to quit 
    
   ![3](https://user-images.githubusercontent.com/77826778/106151760-b4274200-61a2-11eb-94dc-ebe82f5ecea0.PNG)
   
   ngspice plots the graph as shown below.
   ![Capture14](https://user-images.githubusercontent.com/77826778/106092360-21f84d00-6154-11eb-92ef-93401b5c7e86.PNG)
    
   # DAY 4:
   [Theory]
   
   [Lab Exercise]
   
   Grid changes can be done after checking the value in tracks.info
   
   ![Capture15](https://user-images.githubusercontent.com/77826778/106150340-40d10080-61a1-11eb-9df7-bc89d7fc6263.PNG)
    
   This is how the layout looks after changing grid. 
   
   ![1](https://user-images.githubusercontent.com/77826778/106150354-4595b480-61a1-11eb-895e-c677b100ca9b.PNG)
    
   The lef command writes LEF-format files, which are files containing technology information and information about the content of standard cells.
   ![Capture151](https://user-images.githubusercontent.com/77826778/106150371-4a5a6880-61a1-11eb-8346-55bf77769083.PNG)
   
   Slack condition can be met by bringing following changes.
   
   ![2](https://user-images.githubusercontent.com/77826778/106151882-d8831e80-61a2-11eb-9d26-60bff8f9837d.PNG)
   
   # DAY 5:
   [Theory]
   
   Routing - Routing step takes place after placement. It involves connecting metal wires with pins of same signal. DRC (Design Rule Check) must not be violated in this process.    There are two types of routing performed-
   - Fast Route: Performs global routing by dividing it into small boxes. Using this we can analyse congestion.
   - Triton Route: Performs detail routing. It also checks DRC.
   
   DRC- These are set of rules that need to be followed by metal lay to avoid DRC failure.
   
   Parasitic Extraction: This forms a virtual route and estimates congestion using the placement information of standard cells. This is to create an analog model of the circuit.
   
   SPEF is an IEEE standard which can be expanded as Standard Parasitic Exchange Format. They capture parasitic capacitances and resistances of non ideal wires.
   
   # References:
    -https://github.com/nickson-jose/vsdstdcelldesign
    -https://github.com/google/skywater-pdk
    -http://opencircuitdesign.com/
   
   # Acknowledgements:
    ^ Kunal Ghosh, Co-Founder (VSD CORP. PVT. LTD)
    ^ Nickson Jose, Teaching Assistant (VSD CORP. PVT. LTD)

   
   
   
   
   
   
   
   
   
   
   
   
   
  
 
