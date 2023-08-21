Parsing: Abinit
===

[Abinit](https://abinit.org/) is natively supported by [ASE](https://wiki.fysik.dtu.dk/ase/ase/io/formatoptions.html#abinit-output). Both abo and GSR outputs are supported.
There is exemple output for 2 calculations in the files `samples/sample.000001/abinit.abo`, and `samples/sample.000002/abinit.abo` for the abo format, and `samples/sample.000001/abinito_GSR.nc`, `samples/sample.000002/abinito_GSR.nc`

**We need the most recent version of [ASE](https://gitlab.com/ase/ase)**. Please make sure you have that installed, e.g., by running
```bash
pip install git+https://gitlab.com/ase/ase.git@master
```

You can parse the files by running

```bash
tdep_parse_output samples/*/abinit.abo
```
for the abo format, and
```bash
tdep_parse_output samples/*/abinito_GSR.nc
```

Please not the that IO format specification via `--format` is not necessary in this case because both formats are automatically detected to be abinit output by [`ase.io.read`](https://wiki.fysik.dtu.dk/ase/ase/io/io.html#ase.io.read).

The output should be:

```
Parse 2 file(s)
... empty forces will be ignored: False
*** SIMULATION TEMPERATURE IS NOT GIVEN
--> set to -314.15K to remind you
... parse file   1: samples/sample.00001/abinit.abo
... parse file   2: samples/sample.00002/abinit.abo
... found 2 samples
... write forces, positions, and statistics
... forces written to infile.forces
... positions written to infile.positions
... statistics written to infile.stat
... meta info written to infile.meta
```
for the first case, and 
```
Parse 2 file(s)
... empty forces will be ignored: False
*** SIMULATION TEMPERATURE IS NOT GIVEN
--> set to -314.15K to remind you
... parse file   1: samples/sample.00001/abinito_GSR.nc
... parse file   2: samples/sample.00002/abinito_GSR.nc
... found 2 samples
... write forces, positions, and statistics
... forces written to infile.forces
... positions written to infile.positions
... statistics written to infile.stat
... meta info written to infile.meta
```

Inspect these input files. That's it.
