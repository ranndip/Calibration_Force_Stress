# Calibration_Force_Stress
Calibration code for training RANN potentials with added force and stress fitting functionality.

To train a RANN potential, first you must compile the Calibration code. Ensure the Makefile is set up properly for your machine, and run the following:
```sh
make clean
make
```
The -j flag can be added to the make command to use all available cpu cores.

After successful compilation, the executable created can be used to train RANN potentials by running the following:
```sh
./nn_calib_icc_new -in RANN.input
```
Where nn_calib_icc_new is the name of the executable produced (defined in Makefile), and RANN.input is the name of your RANN input file.

If this fails, you may need to adjust the stack size:
```sh
ulimit -s unlimited
export OMP_STACKSIZE=10485760
./nn_calib_icc_new -in RANN.input
```
