# RTL-Design-using-Verilog-using-SKY130-technology <br/>

## Setting up the environment<br/>

Git cloned the file https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git using the following code snippet:<br/>

/home/divyan0436/VLSI <br/>
divyan0436@rtlworkshop-06:~/VLSI$ pwd <br/>
/home/divyan0436/VLSI <br/>
divyan0436@rtlworkshop-06:~/VLSI$ git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git <br/>
Cloning into 'sky130RTLDesignAndSynthesisWorkshop'... <br/>
remote: Enumerating objects: 403, done. <br/>
remote: Counting objects: 100% (55/55), done. <br/>
remote: Compressing objects: 100% (41/41), done. <br/>
remote: Total 403 (delta 14), reused 47 (delta 12), pack-reused 348 <br/>
Receiving objects: 100% (403/403), 7.79 MiB | 9.01 MiB/s, done. <br/>
Resolving deltas: 100% (237/237), done. <br/>


### Contents of the Cloned file: <br/>

divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop$ ls <br/>
DC_WORKSHOP  README.md	my_lib	verilog_files  yosys_run.sh <br/>

#### Content of my_lib: <br/>

divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop$ cd my_lib <br/>
divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib$ ls <br/>
lib  verilog_model <br/>

##### Content of lib: <br/>

divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib$ cd lib <br/>
divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib/lib$ ls <br/>
sky130_fd_sc_hd__tt_025C_1v80.lib <br/>

##### Content of verilog_model: <br/>

divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib$ cd verilog_model/ <br/>
divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model$ ls <br/>
primitives.v  sky130_fd_sc_hd.v <br/>

#### Contents of verilog_files <br/>

divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop$ cd verilog_files <br/>
divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files$ ls <br/>

bad_case.v		    dff_const1.v		multiple_modules_flat.v		tb_comp_case.v		   tb_opt_check.v  <br/>
bad_case_net.v		dff_const2.v		multiple_modules_hier.v		tb_counter_opt.v	   tb_opt_check2.v <br/>
bad_counter.v		  dff_const3.v		mux_generate.v			tb_demux_case.v		   tb_opt_check3.v <br/>
bad_latch.v		    dff_const4.v		mux_spice.v			tb_demux_generate.v	   tb_partial_case_assign.v <br/>
bad_latch_2.v	  	dff_const5.v		net.v				tb_dff_async_set.v	   tb_pattern_detect_fsm.v <br/>
bad_latch_net.v		dff_net.v		    opt_check.v			tb_dff_asyncres.v	   tb_rca.v <br/>
bad_mux.v		      dff_syncres.v		opt_check2.v			tb_dff_asyncres_syncres.v  tb_ripple_counter.v <br/>
bad_mux_net.v		  fa.v			      opt_check3.v			tb_dff_const1.v		   tb_ternary_operator_mux.v <br/>
bad_shift_reg.v		good_counter.v		opt_check4.v			tb_dff_const2.v		   tb_up_dn_cntr.v <br/>
bad_shift_reg2.v	good_latch.v		partial_case_assign.v		tb_dff_const3.v		   tb_up_dn_cntr_with_load.v <br/>
blocking_caveat.v	good_mux.v		pattern_detect_fsm.v		tb_dff_const4.v		   tb_up_dn_cntr_with_load_with_start_stop.v <br/>
blocking_caveat_net.v	good_mux_netlist.v	pattern_detect_fsm_bad_style.v	tb_dff_const5.v		   tb_upcntr.v <br/>
comp_case.v		    good_shift_reg.v	rca.v				tb_dff_syncres.v	   ternary_operator_mux.v <br/>
counter_opt.v		incomp_case.v		ripple_counter.v		tb_good_counter.v	   ternary_operator_mux_net.v <br/>
counter_opt2.v		incomp_if.v		tb_bad_case.v			tb_good_latch.v		   up_dn_cntr.v <br/>
demux_case.v		incomp_if2.v		tb_bad_counter.v		tb_good_mux.v		   up_dn_cntr_with_load.v <br/>
demux_generate.v	mul2_net.v		tb_bad_latch.v			tb_good_shift_reg.v	   up_dn_cntr_with_load_with_start_stop.v <br/>
dff_ares.net.v		mult_2.v		tb_bad_latch2.v			tb_incomp_case.v	   upcntr.v <br/>
dff_async_set.v		mult_8.v		tb_bad_mux.v			tb_incomp_if.v <br/>
dff_asyncres.v		multiple_module_opt.v	tb_bad_shift_reg.v		tb_incomp_if2.v <br/>
dff_asyncres_net.v	multiple_module_opt2.v	tb_bad_shift_reg2.v		tb_multiple_modules.v <br/>
dff_asyncres_syncres.v	multiple_modules.v	tb_blocking_caveat.v		tb_mux_generate.v <br/>

## DAY 1: Introduction to Verilog Design and Synthesis <br/>
Register Transfer Level (RTL) coding is a combination of behavioural and dataflow constructs that are used to specify and test a design. We have a Design module and a Test bench, in design module, we desribe the functionality of the design and in simulation module(or test bench) we provide input to our design module and then verify its functionality.<br/>
![11](https://user-images.githubusercontent.com/87258547/166254497-5a5dc0cf-dbf7-425f-b94e-558464c15a32.png) <br/>
Simulator is the tool used for simulating the design. the simulator used here is **iverilog**. <br/>

![12](https://user-images.githubusercontent.com/87258547/166254565-f5e11e70-36f9-4187-91f8-f08115c90c01.png)

divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files$ iverilog good_mux.v tb_good_mux.v <br/>
divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files$ ./a.out <br/>
VCD info: dumpfile tb_good_mux.vcd opened for output. <br/>
divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files$ gtkwave tb_good_mux.vcd <br/>

<br/>
![good_mux gtkwave](https://user-images.githubusercontent.com/87258547/166254937-d754aacd-f52c-48d4-8204-5e2e638647c2.png) <br/>
<br/>
**Yoysys** is a synthesis tool used to convert RTL into Netlist <br/>
<br/>
![yosys schematic](https://user-images.githubusercontent.com/87258547/166255167-e83be47d-b77b-42cd-8ca4-cd60fe161544.png) <br/>
<br/>



Invoking Yosys: divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files$ yosys <br/>

 /----------------------------------------------------------------------------\  <br/>
 |                                                                            |  <br/>
 |  yosys -- Yosys Open SYnthesis Suite                                       |  <br/>
 |                                                                            |  <br/>
 |  Copyright (C) 2012 - 2020  Claire Xenia Wolf <claire@yosyshq.com>         |  <br/>
 |                                                                            |  <br/>
 |  Permission to use, copy, modify, and/or distribute this software for any  |  <br/>
 |  purpose with or without fee is hereby granted, provided that the above    |  <br/>
 |  copyright notice and this permission notice appear in all copies.         |  <br/>
 |                                                                            |  <br/>
 |  THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES  |  <br/>
 |  WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF          |  <br/>
 |  MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR   |  <br/>
 |  ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES    |  <br/>
 |  WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN     |  <br/>
 |  ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF   |  <br/>
 |  OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.            |  <br/>
 |                                                                            |  <br/>
 \----------------------------------------------------------------------------/  <br/>

 Yosys 0.9+4081 (git sha1 862e84eb, gcc 7.5.0-3ubuntu1~18.04 -fPIC -Os) <br/>

### READING THE SKY130 LIBRARY: <br/>

yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib  <br/>
1. Executing Liberty frontend.                    <br/>
Imported 428 cell types from liberty file.        <br/>


### Reading verilog file:<br/>


yosys> read_verilog good_mux.v <br/>

Printing statistics. <br/>

=== good_mux ===<br/>

   Number of wires:                  4 <br/>
   Number of wire bits:              4 <br/>
   Number of public wires:           4 <br/>
   Number of public wire bits:       4 <br/>
   Number of memories:               0 <br/>
   Number of memory bits:            0 <br/>
   Number of processes:              0 <br/>
   Number of cells:                  1 <br/>
     $_MUX_                          1 <br/>


GENERATING THE NETLIST: (ABC CONVERTS RTL TO GATE) <br/>


yosys> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib <br/>
The netlist obtained is: <br/>
ABC RESULTS:   sky130_fd_sc_hd__mux2_1 cells:        1  <br/>
ABC RESULTS:        internal signals:                0  <br/>
ABC RESULTS:           input signals:                3  <br/>
ABC RESULTS:          output signals:                1  <br/>
Removing temp directory.                                <br/>


yosys> show  <br/>
<br/>
![synthesis tool output good_mux](https://user-images.githubusercontent.com/87258547/166255337-57dab1fe-78ff-474a-b782-96f9a3e46b10.png) <br/>
<br/>

yosys> write_verilog -noattr good_mux_netlist.v <br/>
yosys> !gvim good_mux_netlist.v <br/>
<br/>
![good_mux_netlist](https://user-images.githubusercontent.com/87258547/166255095-11a7bf41-51ef-4e54-aec6-b60c219d1a6d.png) <br/>
<br/>

## DAY 2: Timing Libs, Hierarchical VS Flat Sythesis abd Efficient Flop Coding Styles  <br/>

![t1](https://user-images.githubusercontent.com/87258547/166259588-c8824cf9-ca80-4535-bfed-316ced2d3ecb.png)  <br/>
![t2](https://user-images.githubusercontent.com/87258547/166259613-02200c31-6b2f-44c3-b0e1-7c810d4c0d6b.png)  <br/>
![t3](https://user-images.githubusercontent.com/87258547/166259648-e552ac1b-4f65-4ba5-8090-7838b0ee33d4.png)  <br/>
![t4](https://user-images.githubusercontent.com/87258547/166259745-6271b88b-a4fe-4405-a29f-66817a4c31de.png)  <br/>


divyan0436@rtlworkshop-06:~/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files$ gvim multiple_modules.v  <br/>


yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib  <br/>

yosys> read_verilog multiple_modules.v

yosys> synth -top multiple_modules

3.25. Printing statistics.

=== multiple_modules ===

   Number of wires:                  5
   Number of wire bits:              5
   Number of public wires:           5
   Number of public wire bits:       5
   Number of memories:               0
   Number of memory bits:            0
   Number of processes:              0
   Number of cells:                  2
     sub_module1                     1
     sub_module2                     1

=== sub_module1 ===

   Number of wires:                  3
   Number of wire bits:              3
   Number of public wires:           3
   Number of public wire bits:       3
   Number of memories:               0
   Number of memory bits:            0
   Number of processes:              0
   Number of cells:                  1
     $_AND_                          1

=== sub_module2 ===

   Number of wires:                  3
   Number of wire bits:              3
   Number of public wires:           3
   Number of public wire bits:       3
   Number of memories:               0
   Number of memory bits:            0
   Number of processes:              0
   Number of cells:                  1
     $_OR_                           1

=== design hierarchy ===

   multiple_modules                  1
     sub_module1                     1
     sub_module2                     1

   Number of wires:                 11
   Number of wire bits:             11
   Number of public wires:          11
   Number of public wire bits:      11
   Number of memories:               0
   Number of memory bits:            0
   Number of processes:              0
   Number of cells:                  2
     $_AND_                          1
     $_OR_                           1


yosys> flatten

yosys> write_verilog multiple_modules_flat.v

yosys> write_verilog -noattr multiple_modules_flat.v

yosys> !gvim multiple_modules_flat.v
