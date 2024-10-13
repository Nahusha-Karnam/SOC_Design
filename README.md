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

</details>
