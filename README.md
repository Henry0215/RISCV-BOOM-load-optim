# RISCV-BOOM-load-optim
a load optimization scheme for CPU, implemented in RISCV-BOOM.

# 使用方法
   本方案基于BOOM 环境开发，使用前请对齐环境版本 chipyard1.7.0, 对应BOOM https://github.com/riscv-boom/riscv-boom/blob/ad64c5419151e5e886daee7084d8399713b46b4b。
   vivado-riscv-v的commit id: commit c488d6221f06ba27cd2892b30b2027027b5f54c7。
   在准备好之后先执行：
    ```bash
    export PATH=$PATH:/opt/Xilinx/Vivado/2021.1/bin
    ```
    将vivado加入环境变量，方便后续编译比特流。
    之后进入vivado-riscv-v目录，并将你需要的BOOM代码替换掉路径``vivado-risc-v/generators/riscv-boom/src/main/scala``下的代码，最后执行：
    ```bash
    make CONFIG=Rocket64x1 BOARD=genesys2 bitstream
    ```
    等待编译结果，编译成功后会在路径``vivado-risc-v/workspace/Rocket64x1/vivado-genesys2-riscv/genesys2-riscv.runs/impl_1/riscv_wrapper.bit``下生成编译好的比特流文件，可以通过scp传输到主机，烧录到FPGA上进行测试。
    需要注意的是，编译过程可能会比较长，具体时间取决于你的计算机性能和编译环境的配置，请耐心等待。
