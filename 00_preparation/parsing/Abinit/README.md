Parsing: FHI-aims
===

[Abinit](https://abinit.org/) is natively supported by [ASE](https://wiki.fysik.dtu.dk/ase/ase/io/formatoptions.html#abinit-output). Both abo and GSR outputs are supported.
There is exemple output for 2 calculations in the files `samples/sample.000001/abinit.abo`, and `samples/sample.000002/abinit.abo` for the abo format, and `samples/sample.000001/abinito_GSR.nc`, `samples/sample.000002/abinito_GSR.nc`

You can parse the files by running

```bash
tdep_parse_output samples/*/abinit.abo --format abinit-out
```
for the abo format, and
```bash
tdep_parse_output samples/*/abinito_GSR.nc --format abinit-gsr
```

Please not the that IO format specification via `--format` is necessary in this case because both formats are not automatically detected to be abinit output by [`ase.io.read`](https://wiki.fysik.dtu.dk/ase/ase/io/io.html#ase.io.read).

The output should be:

```
Parse 2 file(s)
... empty forces will be ignored: False
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
