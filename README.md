![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/test/badge.svg) ![](../../workflows/fpga/badge.svg)

# Tiny Tapeout Logic Project Sample
This is a sample project for the logic circuit of the TinyTapeout SKY130.

# Set up the Development Environment on Ubuntu22.04


## Setup Variable
```
export PDK_ROOT=~/pdk/
export PDK=sky130A
export LIBRELANE_TAG=2.4.2
```

## Setup Softwares
```
sudo apt install python3.10-venv python3-tk librsvg2-bin pngquant make iverilog
mkdir ~/ttsetup
python3 -m venv ~/ttsetup/venv
source ~/ttsetup/venv/bin/activate
git clone https://github.com/noritsuna/ttsky-verilog-sample_counter
cd ttsky-verilog-sample_counter
git clone https://github.com/TinyTapeout/tt-support-tools tt
pip install -r ./tt/requirements.txt
pip install librelane==$LIBRELANE_TAG


## Initial Config
```
cd ttsky-verilog-sample_counter
./tt/tt_tool.py --create-user-config
```

## Build Project
`./tt/tt_tool.py --harden`


## Run Test
```
cd ttsky-verilog-sample_counter/test
pip install -r requirements.txt
make -B
```
