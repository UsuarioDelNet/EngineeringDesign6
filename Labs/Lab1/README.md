# Engineering Design VI `CPE 322-A`
## Lab 1 — GHDL and GTKWave
---
### Half Adder Example

```sh
$ ghdl -a ha.vhd
$ ghdl -a ha_tb.vhd
$ ghdl -e ha_tb
$ ghdl -r ha_tb --vcd=ha.vcd
ha_tb.vhdl:47:5:@5ns:(assertion error): Reached end of test
$ gtkwave ha.vcd
```
![Half Adder Powershell](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab1/SourcesLab1/HaPowershell.png)
![GTKWave Half Adder](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab1/SourcesLab1/GTKWaveHa.png)
