# Digital VLSI SoC design and planning
### Day-1 
#### Inception of open source EDA, OpenLANE and Sky130 PDK
<details>
<summary> Theory </summary>
<br>
  
![image](https://github.com/user-attachments/assets/58829de8-3a23-4695-aec7-2736b3112cc8)
Introduction to packages

![image](https://github.com/user-attachments/assets/0d23a36e-3ef8-4609-8f6c-995f15e074b9)
Introduction to die's and understanding Macros and Foundry IP's

![image](https://github.com/user-attachments/assets/180f703e-c24e-4cfd-b925-ed29ecf3ed4a)
Understanding how applications run and the flow of how programs convert into machine level language

![image](https://github.com/user-attachments/assets/bf0f0220-2d3d-45aa-970c-49d08b404767)
Purpose and Understanding Register Transfer Level

![image](https://github.com/user-attachments/assets/689553f5-b0df-4aa4-a4f7-cb6d762c7e4c)
Introduction to Opensource tools and understanding PDKs

![image](https://github.com/user-attachments/assets/682cf979-ab92-421d-a1a3-b93ecbe7174b)
Understanding RTL to GDSII design flow

![image](https://github.com/user-attachments/assets/ce337c48-9777-405e-af9b-2e5190d22c7e)
Understanding OpenLANE ASIC Design flow

![image](https://github.com/user-attachments/assets/907a299b-aa70-4942-b783-5786aa1433cf)
Design for testing and what is scan chain

![image](https://github.com/user-attachments/assets/ff5a131e-cf06-4742-8966-f66572ac26c0)
Understanding Antenna rules violation
</details>

<details>
<summary> Lab </summary>
<br>
Linux Commands for Opening OpenLANE

```
cd work/tools/openlane_working_dir/openlane

./flow.tcl -interactive

docker

package require openlane 0.9

prep -design picorv32a

run_synthesis
```
Running Synthesis

![image](https://github.com/user-attachments/assets/9d276fb0-a1ab-4c92-ac85-e2a5c98cc319)

![image](https://github.com/user-attachments/assets/5a8037d3-45ef-4f76-842f-6dbf16277edf)

Number of D Flip Flop = 1613
Total number of cells = 14876

Calculating Flop ratio = no.of d-flipflop/total cells
```
Flop ratio = 1613/14876
Flop ratio = 0.108429
```
%of D Flip Flops in the area = 10.8429 %
</details>


### Day-2
#### Floor Planning
<details>
<summary> Theory Session-1 </summary>

![image](https://github.com/user-attachments/assets/750b33e2-0bd8-4be1-8022-0857c44d4c01)
Understanding Utilization factor and aspect ratio

![image](https://github.com/user-attachments/assets/2c372b15-e183-461c-a271-e0a23a74e633)
Making and using custom blocks or ready foundry IP blocks

![image](https://github.com/user-attachments/assets/7df77654-a011-45a3-9091-ddcc69f54cb8)
Understanding Noise Margin

![image](https://github.com/user-attachments/assets/4b264b5a-39d8-4e2d-8b2d-0239f34973c0)
Concept and Purpose of Decoupling capacitors

![image](https://github.com/user-attachments/assets/a3b4e2b1-c110-446f-8925-139b1f9f4b83)
Concept of Power Planning and it's purpose
Concept of Power mesh

![image](https://github.com/user-attachments/assets/894330ee-cf16-468f-b836-e29df4498b12)
Concept of Pin Placement and lowering resistance with higher width
</details>

<details>
<summary> Lab Session-1 </summary>
Floor Planning
  
```
run_floorplan
```
![image](https://github.com/user-attachments/assets/ff026aa5-2eed-439d-832e-13b3a6dc0219)

![image](https://github.com/user-attachments/assets/4198717a-6594-4f34-8786-64291596f23e)

Checking Design Exchange Format
![image](https://github.com/user-attachments/assets/460107d7-99f2-437b-bea4-79f4460615a8)

Seeing Die area
![image](https://github.com/user-attachments/assets/c7163036-c115-42c7-8084-6503f75d4173)

Steps to Open Magic
```
magic -T /home/vsduser//Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```

Launching Magic
![image](https://github.com/user-attachments/assets/4d647c9c-c1de-43ca-abd7-2b8d310b08d9)


</details>


<details>
<summary> Theory Session-2 </summary>
  
![image](https://github.com/user-attachments/assets/4cfa018d-9a10-4c1e-83fb-05a3524f86c3)
Understanding Library cells and Cell shapes

![image](https://github.com/user-attachments/assets/60f461f7-f91c-4a06-959b-126bc56a3a06)
Converting netlist to actual advanced floor plan design


</details>

<details>
<summary> Lab Session-2 </summary>

``` 
run_placement
```
![image](https://github.com/user-attachments/assets/0e4de76b-527a-45f0-801b-21a44ac3f1a8)

```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

```
Running Magic
![image](https://github.com/user-attachments/assets/e33600b4-13a6-4ea1-a0c9-47ef40697a07)

![image](https://github.com/user-attachments/assets/91b2752d-9a8a-46b1-9f6e-7f4fbceb3fec)
  
</details>

<details>
<summary> Theory Session-3</summary>
  
![image](https://github.com/user-attachments/assets/7fed6fe6-f8ff-4cfb-aa54-8026eb3ff437)
Understanding Cell design flow and Foundry rules

![image](https://github.com/user-attachments/assets/fa5f3d79-7513-4f1f-89ba-35d961e459a1)
Understanding SPICE Parameters

![image](https://github.com/user-attachments/assets/ae1807d2-7310-44ca-afa6-e6c86b796f9a)
Understanding User defined specifications

![image](https://github.com/user-attachments/assets/a1f01b94-49b2-4971-b973-ed41b9bacfaf)
Understanding cicuit design and layout design

![image](https://github.com/user-attachments/assets/ae78bab2-b992-4efd-9896-d20bdac1eb33)
Understanding Characterization flow

![image](https://github.com/user-attachments/assets/25004281-7f45-4aa3-879e-f8c7adc8d9f8)
Understanding Timing Characterization

![image](https://github.com/user-attachments/assets/f6c7df5f-cb94-4209-9aa2-7ac2b1178224)
Understanding propogation delay

</details>

### Day-3
#### Library cell design

<details>
<summary> Theory </summary>

![image](https://github.com/user-attachments/assets/04af8bbb-cb1e-4632-87e2-50ff73941243)
Understanding SPICE Deck specification

![image](https://github.com/user-attachments/assets/d6c54b19-6f57-403b-ad0a-139c0d505d9b)
Understanding SPICE Deck simulation

![image](https://github.com/user-attachments/assets/4fca8092-b044-4633-9520-da73e072bab7)
Understanding Delay calculation
</details>

<details>
<summary> Lab </summary>

```
git clone https://github.com/nickson-jose/vsdstdcelldesign
```

```
magic -T sky130A.tech sky130_inv.mag &
```

![image](https://github.com/user-attachments/assets/e9cb96fb-ff1e-41d3-8d49-cab2f9754f42)
Cloned Inverter

Extracted the SPICE file

```
extract all
```

```
ext2spice cthresh 0 rthresh 0
```

```
ext2spice
```
![image](https://github.com/user-attachments/assets/7cb6c3bc-1e53-4a0f-be3b-4c6c37f6a890)

![image](https://github.com/user-attachments/assets/1742c6c1-b841-47da-9c3a-7ecd11d2b911)

```
gedit sky130_inv.spice
```

```
ngspice sky130_inv.spice

```

![image](https://github.com/user-attachments/assets/a89e53af-a35a-478b-8d80-47d2c797ed43)
Defining ngspice specification

![image](https://github.com/user-attachments/assets/30251f60-b0ba-47d1-a518-602c8943fc88)

```
plot y vs time a
```

![image](https://github.com/user-attachments/assets/7d1a48c3-13e5-4fd4-b118-7d1b6e9ee6af)


Rise Time = (2.24508-2.182) = 0.06308
Fall Time = (2.20917-2.1511) = 0.05806

![image](https://github.com/user-attachments/assets/b04d2bcc-d054-483a-9d03-f7cb473a0671)
Opening Magic in better graphics

```
cd
```

```
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
```

```
tar xfz drc_tests.tgz
```

```
cd drc_tests
```

```
ls -al
```

```
gvim .magicrc
```

```
magic -d XR &
```
Resolving poly.9 error
![image](https://github.com/user-attachments/assets/11c00987-9ce3-4243-bac6-4cd00ccbd0c4)

Resolving difftap error
![image](https://github.com/user-attachments/assets/8b83a6fa-5650-4265-b729-ed25d646917a)

![image](https://github.com/user-attachments/assets/b7cba596-fe56-4784-a689-e9f4a680c731)

Resolving nwell error
![image](https://github.com/user-attachments/assets/a4513dd9-8dd5-4501-b506-21eeda0a7cc2)

![image](https://github.com/user-attachments/assets/01b90e0c-9514-46b8-b64c-015903d46fdb)


</details>

### Day 4
<details>
<Summary> Lab </Summary>

```
cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
```

```
magic -T sky130A.tech sky130_inv.mag &
```

In tikicon window
```
help grid
```

```
grid 0.46um 0.34um 0.23um 0.17um
```

![image](https://github.com/user-attachments/assets/16ff1a7c-6424-4fac-98e4-0edf984244bf)

```
save sky130_vsdinv.mag

```

```
magic -T sky130A.tech sky130_vsdinv.mag &
```

```
lef write
```

```
cp sky130_vsdinv.lef ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
```

```
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
```

```
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
```

```
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
```

for lef file
```
set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
```

Editing the Config.tcl file
![image](https://github.com/user-attachments/assets/f7bb750b-4a56-4973-bb66-c9ab410cd6aa)

```
cd Desktop/work/tools/openlane_working_dir/openlane

```

```
docker
```

```
./flow.tcl -interactive
```

```
package require openlane 0.9
```


```
prep -design picorv32a
```


```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
```

```
add_lefs -src $lefs
```

```
run_synthesis
```
Successfully run synthesis
![image](https://github.com/user-attachments/assets/7937a0e2-d3f5-483e-b784-6489fd0012fe)


Noteing down values
![image](https://github.com/user-attachments/assets/a491f0e7-ff8d-47fe-ab06-e565e180eeba)

![image](https://github.com/user-attachments/assets/a350b25c-a4c2-4bd8-91b5-d69fc06f52ce)


```
prep -design picorv32a -tag 16-10_13-08 -overwrite
```

```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
```

```
add_lefs -src $lefs
```

```
echo $::env(SYNTH_STRATEGY)
```

```
set ::env(SYNTH_STRATEGY) "DELAY 3"
```

```
echo $::env(SYNTH_BUFFERING)
```

```
echo $::env(SYNTH_SIZING)
```

```
set ::env(SYNTH_SIZING) 1
```

```
echo $::env(SYNTH_DRIVING_CELL)
```

```
run_synthesis
```

Re running synthesis
![image](https://github.com/user-attachments/assets/e55ded37-a68b-4180-a9ec-2b022223d960)

![image](https://github.com/user-attachments/assets/306cd0c3-3b43-4ee9-b438-1b39c28b378e)

```
run_floorplan
```

```
init_floorplan
```

```
place_io
```

```
tap_decap_or
```

```
run_placement
```

Sucessfully run synthesis and placement
![image](https://github.com/user-attachments/assets/ad924db7-e92f-43d5-be94-633283b918e2)

```
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-10_13-08/results/placement/

```

```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```


Opening magic
![image](https://github.com/user-attachments/assets/c2f4399e-a1aa-4119-babe-c8bdb0af6701)

Expanding the vsd_inv
![image](https://github.com/user-attachments/assets/d5f539fa-af7e-4e91-8c91-894f38b12059)

```
prep -design picorv32a -tag 16-10_13-08 -overwrite
```

```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
```

```
add_lefs -src $lefs
```

```
echo $::env(SYNTH_STRATEGY)
```

```
set ::env(SYNTH_STRATEGY) "DELAY 3"
```

```
echo $::env(SYNTH_BUFFERING)
```

```
echo $::env(SYNTH_SIZING)
```

```
set ::env(SYNTH_SIZING) 1
```

```
echo $::env(SYNTH_DRIVING_CELL)
```

```
run_synthesis
```






Creating pre_sta.conf file
![image](https://github.com/user-attachments/assets/0db06bff-ad0d-4165-86b7-822a9863ffb2)

Creating my_base.sdc file
![image](https://github.com/user-attachments/assets/9fa9e74a-760f-4fe9-be22-8db33a9f13bc)

```
cd Desktop/work/tools/openlane_working_dir/openlane

```

```
sta pre_sta.conf
```

![image](https://github.com/user-attachments/assets/24fe18d5-5277-45f0-865f-fc288650abf0)

![image](https://github.com/user-attachments/assets/ba1d4b93-f206-4745-bdb4-c738fc8da493)

![image](https://github.com/user-attachments/assets/ea531b54-2e24-423e-8d0a-6c0197992df6)

![image](https://github.com/user-attachments/assets/b9780d37-cebd-486d-8c30-50d7cb2e30a7)


Reducing slack
![image](https://github.com/user-attachments/assets/623f58d5-04d7-41d3-84b5-5e5f530ade6a)

```
report_net -connections _11672_

```

```
help replace_cell
```

```
replace_cell _14510_ sky130_fd_sc_hd__or3_4
```

```
report_checks -fields {net cap slew input_pins} -digits 4
```

![image](https://github.com/user-attachments/assets/7e56e4d0-7eef-4c4f-a200-5b18c7daef03)

```
report_net -connections _11675_

```

```
replace_cell _14514_ sky130_fd_sc_hd__or3_4

```

```
report_checks -fields {net cap slew input_pins} -digits 4

```

![image](https://github.com/user-attachments/assets/60d66fc2-2825-4905-85ba-e4dcb2cb2e5f)

```
report_net -connections _11643_

```

```
replace_cell _14481_ sky130_fd_sc_hd__or4_4

```

```
report_checks -fields {net cap slew input_pins} -digits 4

```

![image](https://github.com/user-attachments/assets/5ecf558c-3c93-4cd7-b209-4ece6fafbdcd)

```
report_net -connections _11668_

```

```
replace_cell _14506_ sky130_fd_sc_hd__or4_4

```

```
report_checks -fields {net cap slew input_pins} -digits 4

```



Reduced slack to -22.6173

![image](https://github.com/user-attachments/assets/3ee2d6bf-13f3-4716-a730-e13c17a6d665)

```
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-10_13-08/results/synthesis/

```

```
ls
```

```
cp picorv32a.synthesis.v picorv32a.synthesis_old.v
```

```
ls
```

```
help write_verilog

```

```
write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/picorv32a.synthesis.v
```

```
exit
```


Writing verilog
![image](https://github.com/user-attachments/assets/1faf57a1-6ff3-4c24-ac1a-f404cf86059a)


```
prep -design picorv32a -tag 16-10_13-08 -overwrite
```

```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
```

```
add_lefs -src $lefs
```

```
echo $::env(SYNTH_STRATEGY)
```

```
set ::env(SYNTH_STRATEGY) "DELAY 3"
```

```
echo $::env(SYNTH_BUFFERING)
```

```
echo $::env(SYNTH_SIZING)
```

```
set ::env(SYNTH_SIZING) 1
```

```
echo $::env(SYNTH_DRIVING_CELL)
```

```
run_synthesis
```

Clock tree synthesis done
![image](https://github.com/user-attachments/assets/f0ea2fda-a0ac-4388-b045-62cd0924f0cc)


```
openroad
```

```
read_lef /openLANE_flow/designs/picorv32a/runs/24-03_10-03/tmp/merged.lef
```

```
read_def /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/cts/picorv32a.cts.def
```

```
write_db pico_cts.db
```

```
read_db pico_cts.db

```

```
read_verilog /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/synthesis/picorv32a.synthesis_cts.v
```
```
read_liberty $::env(LIB_SYNTH_COMPLETE)
```
```
link_design picorv32a
```

```
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

```
```
set_propagated_clock [all_clocks]
```
```
help report_checks

```
```
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4
```
```
exit
```

Post CTS timing analysis
![image](https://github.com/user-attachments/assets/7a641653-c750-46a5-917f-57cbaa5473ae)


```
echo $::env(CTS_CLK_BUFFER_LIST)
```
```
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]
```
```
echo $::env(CTS_CLK_BUFFER_LIST)
```
```
echo $::env(CURRENT_DEF)
```
```
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/placement/picorv32a.placement.def
```
```
run_cts
```
```
echo $::env(CTS_CLK_BUFFER_LIST)
```
```
openroad
```
```
read_lef /openLANE_flow/designs/picorv32a/runs/24-03_10-03/tmp/merged.lef
```
```
read_def /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/cts/picorv32a.cts.def
```
```
write_db pico_cts1.db
```
```
openROAD

```
```
read_db pico_cts.db
```
```
read_verilog /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/synthesis/picorv32a.synthesis_cts.v
```
```
read_liberty $::env(LIB_SYNTH_COMPLETE)
```
```
link_design picorv32a
```
```
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
```
```
set_propagated_clock [all_clocks]
```
```
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4
```
```
report_clock_skew -hold
```
```
report_clock_skew -setup
```
```
exit
```
```
echo $::env(CTS_CLK_BUFFER_LIST)
```
```
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]

```
```
echo $::env(CTS_CLK_BUFFER_LIST)
```

Running CTS again
![image](https://github.com/user-attachments/assets/5f725795-5200-4052-9861-ebd209194d92)
</details>

### Day 5

<details>
<summary> Lab </summary>
  
```
cd Desktop/work/tools/openlane_working_dir/openlane
```
```
docker
```
```
./flow.tcl -interactive

```
```
package require openlane 0.9
```


```
prep -design picorv32a
```
```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]

```
```

add_lefs -src $lefs

```
```
set ::env(SYNTH_STRATEGY) "DELAY 3"
```
```
set ::env(SYNTH_SIZING) 1
```
```
run_synthesis
```
```
init_floorplan

```
```
place_io

```
```
tap_decap_or
```
```
run_placement
```
```
unset ::env(LIB_CTS)
```
```
run_cts

```
```
gen_pdn 

```




Generated PDN
![image](https://github.com/user-attachments/assets/0b4f0bde-6a74-4f0e-b445-1ad0f04728f5)


```
run_routing
```


Finished routing
![image](https://github.com/user-attachments/assets/56780b2a-612e-4eac-9ee9-45f890b96f1b)

```
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-10_13-08/results/routing/
```

```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.def &

```

![image](https://github.com/user-attachments/assets/7a662edb-becc-4ea4-9a77-4e0ef30c6a7a)

No DRC violations
![image](https://github.com/user-attachments/assets/3c863042-4d1c-4db9-8ea8-6e67e992f024)

```
cd Desktop/work/tools/openlane_working_dir/openlane/scripts/spef_extractor

```

```
python3 main.py --def_file /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-10_13-08/results/routing/picorv32a.def
--lef_file /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-10_13-08/tmp/merged.lef 

```

Extracting lef and def file
![image](https://github.com/user-attachments/assets/bd6e8b55-7295-4dac-9a91-affc7be185cb)


```
openroad
```
```
read_lef /openLANE_flow/designs/picorv32a/runs/16-10_13-08/tmp/merged.lef
```
```
read_def /openLANE_flow/designs/picorv32a/runs/16-10_13-08/results/routing/picorv32a.def
```
```
write_db pico_route.db
```
```
read_db pico_route.db
```
```
read_verilog /openLANE_flow/designs/picorv32a/runs/16-10_13-08/results/synthesis/picorv32a.synthesis_preroute.v
```
```
read_liberty $::env(LIB_SYNTH_COMPLETE)
```
```
link_design picorv32a
```
```
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
```
```
set_propagated_clock [all_clocks]
```
```
read_spef /openLANE_flow/designs/picorv32a/runs/16-10_13-08/results/routing/picorv32a.spef
```
```
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4
```
```
exit

```


Generating Report
![image](https://github.com/user-attachments/assets/7c035dac-5633-4582-9604-88bcba486dcb)

![image](https://github.com/user-attachments/assets/4714c480-6d7b-4859-805a-f025d98e382e)


</details>
