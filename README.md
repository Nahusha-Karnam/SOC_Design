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
<summary> Theory </summary>

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
<summary> Lab </summary>
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
