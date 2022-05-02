# RTL-Design-using-Verilog-using-SKY130-technology
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
<br/>
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
