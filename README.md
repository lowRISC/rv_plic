# Deprecated

This repository has been archived. Please refer to the [OpenTitan
PLIC](https://github.com/lowRISC/opentitan/tree/master/hw/ip/rv_plic) instead.

# RISC-V Platform-Level Interrupt Controller

RV_PLIC module is to manage multiple interrupt events generated from the
peripherals. It implements [Platform-Level Interrupt Controller in RISC-V
Privileges specification Section
7](https://people.eecs.berkeley.edu/~krste/papers/riscv-privileged-v1.9.pdf#page=73).

## `reg_rv_plic.py`

The tool is to create register hjson and top module `rv_plic.sv` files given
values of number of sources, number of targets, and max value of priority. By
default `target` is **1** and `priority` is **7** (8 level of priorities
supported)

To change the value and to re-create hjson,

    $ reg_rv_plic.py -s 64 -t 2 -p 15 rv_plic_reg.tpl.hjson > rv_plic_reg.hjson
    $ reg_rv_plic.py -s 64 -t 2 -p 15 rv_plic.tpl.sv > ../rtl/rv_plic.sv

