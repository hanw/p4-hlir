p4-hlir
==========

To install:  
sudo python setup.py install

To run validate tool:  
p4-validate \<path_to_p4_program\>

To open a Python shell with an HLIR instance accessible:  
p4-shell \<path_to_p4_program\>

To build the HLIR and access its objects:  
from p4_hlir.main import HLIR  
h = HLIR(\<path_to_p4_program\>)  
h.build()

You can then access the different P4 top level objects using these Python
OrderedDict's:  
h.p4_actions  
h.p4_control_flows  
h.p4_headers  
h.p4_header_instances  
h.p4_fields  
h.p4_field_lists  
h.p4_field_list_calculations  
h.p4_parser_exceptions  
h.p4_parse_value_sets  
h.p4_parse_states  
h.p4_counters  
h.p4_meters  
h.p4_registers  
h.p4_nodes  
h.p4_tables  
h.p4_action_profiles  
h.p4_action_selectors  
h.p4_conditional_nodes  

The ingress entry points are stored in a dictionary:  
h.p4_ingress_ptr

The egress entry point is:  
h.p4_egress_ptr


To access the P4 types you can use the following import:  
import p4_hlir.hlir.p4 as p4


# Getting the graphs

To get the table graph or parse graph for a P4 program, use:  
p4-graphs \<path_to_p4_program\>

# Compiling to EBPF

There are multiple back-ends that can consume the HLIR P4 program representation.
A compiler back-end which compiles programs expressed in a restricted subset of P4
into eBPF programs that can be run in the Linux kernel can be found at
https://github.com/iovisor/bcc/tree/master/src/cc/frontends/p4
