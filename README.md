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
