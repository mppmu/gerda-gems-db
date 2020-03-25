# Detector n+ surface sampling

Vertices for `nplus_chanwise` simulations are placed here. As Geant4 does not
efficiently sample complex surfaces (especially boolean solids) the Generic
Surface Sampler (GSS) is used. The resulting vertices are stored as (x,y,z)
coordinates in a ROOT file.

These vertices for n+ contact surfaces are obtained by extraction from the
total detector surfaces placed under `gedet/surf_chanwise/ver/`. Processing
is performed by the `GeMS.jl` Julia module.

To get the actual number of events for each file you can run the following
command into this folder:

```console
$ for f in `ls *.root`; do
for> root $f << EOF
for heredoc> auto GSSTree = dynamic_cast<TTree*>(_file0->Get("GSSTree"));
for heredoc> cout << "$f" << '\t' << GSSTree->GetEntries() << '\n';
for heredoc> EOF
```

The areas of the n+ and p+ contacts, for each detector, can be calculated with
the `GeMS.calculate_detector_surfaces` script.
