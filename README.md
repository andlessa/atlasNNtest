# atlasNN
Repository for running the ATLAS-SUSY-2019-04 analysis using SimpleAnalysis


1. Install the analysis:

```
docker pull gitlab-registry.cern.ch/atlas-sa/simple-analysis
```

2. Generate a root file using MG5+HepMC+Delphes.

3. Convert the Delphes root file to a trimmed root file:

```
Delphes2SA.py <input Delphes file> <Output SA file>
```

4. Run simpleAnalysis using docker (with the current folder mounted):

