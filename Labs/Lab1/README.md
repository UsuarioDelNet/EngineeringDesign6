# Engineering Design VI `CPE 322-A`
## Lab 1 — GHDL and GTKWave
---
### Half Adder Example
```Half Adder CMD
$ ghdl -a ha.vhd
$ ghdl -a ha_tb.vhd
$ ghdl -e ha_tb
$ ghdl -r ha_tb --vcd=ha.vcd
ha_tb.vhdl:47:5:@5ns:(assertion error): Reached end of test
$ gtkwave ha.vcd
```
![Half Adder Powershell](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab1/SourcesLab1/HaPowershell.png)
![GTKWave Half Adder](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab1/SourcesLab1/GTKWaveHa.png)
<br />
<br />
---
### T Flip Flop Example
```T Flip Flop CMD
$ ghdl -a tff.vhd
$ ghdl -a tff_tb.vhd
$ ghdl -e tff_tb
$ ghdl -r tff_tb --vcd=tff.vcd
$ gtkwave tff.vcd
```
![T Flip Flop Powershell](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab1/SourcesLab1/TffPowershell.png)
![GTKWave T Flip Flop](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab1/SourcesLab1/GTKWaveTff.png)
<br />
<br />
---
#### Postscript
- All my source files were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/dsd/tree/master/ghdl)
- Alternatively, they can be found in my [`CodeLab1 File`](https://github.com/UsuarioDelNet/EngineeringDesign6/tree/main/Labs/Lab1/CodeLab1)
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
