<img src=".github/gerda-logo.png" align="left" height="80"/>

# gerda-gems-db [![CI](https://github.com/mppmu/gerda-gems-db/actions/workflows/ci.yml/badge.svg)](https://github.com/mppmu/gerda-gems-db/actions/workflows/ci.yml)

GeMS database for GERDA MaGe simulations.

The aim of this repository is to provide a mirror of the structure
of the `/lfs/l1/gerda/gerda-simulations/gerda-gems-db` database at the
`lfs1.mpi-hd.mpg.de` Heidelberg HPC cluster (MPIK) containing official Monte Carlo
simulations of background contaminations for GERDA. It can be easily browsed to
check the current status of the simulations (what has been simulated and what
has not). The database is managed through a tree of JSON metadata files, that
specify how the simulations should be performed. A separate software suite,
available at [mppmu/gerda-gems-sw](https://github.com/mppmu/gerda-gems-sw),
takes care of parsing the metadata and populating the database with corresponding
MaGe macros and output, eventually submitting simulation jobs to the batch system,
in a high-level automatized fashion.

### Related software
* [gerda-gems-sw](https://github.com/mppmu/gerda-gems-sw)
* [gerda-pdfs](https://github.com/mppmu/gerda-pdfs)
* [(GERDA) MaGe source code repository](https://github.com/mppmu/MaGe/tree/gerda-optical)
