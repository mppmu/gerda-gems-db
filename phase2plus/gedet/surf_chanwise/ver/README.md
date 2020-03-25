# Detector surface sampling

Vertices for `surf_chanwise` simulations are placed here, corresponding macro
files can be found under `log/`. As Geant4 does not efficiently sample complex
surfaces (especially boolean solids) the Generic Surface Sampler (GSS) is used.
The resulting vertices are stored as (x,y,z) coordinates in a ROOT file.

The simulations are further processed to extract p+ and n+ surfaces under
`gedet/pplus_chanwise/ver` and `gedet/nplus_chanwise/ver/`.

To get the actual number of events for each file you can run the following
command into this folder:

```console
$ for f in `ls *.root`; do
for> root $f << EOF
for heredoc> auto GSSTree = dynamic_cast<TTree*>(_file0->Get("GSSTree"));
for heredoc> cout << "$f" << '\t' << GSSTree->GetEntries() << '\n';
for heredoc> EOF
for> done
```
