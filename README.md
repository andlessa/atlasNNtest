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

```
docker run -it -v <full path to current folder>:/workdir/atlasNN  gitlab-registry.cern.ch/atlas-sa/simple-analysis
```

5. Inside the docker enviroment copy the atlasNN/SimpleAnalysisCodes folder to workdir:

```
docker> cp -r atlasNN/SimpleAnalysisCodes ./
```

6. Finally run simpleAnalysis:

```
docker> simpleAnalysis -a OneLeptonMultiJets2018 atlasNN/<converted root file>
```

The output will be stored in OneLeptonMultiJets2018.txt and OneLeptonMultiJets2018.root.
Move them to the local folder to keep them after exiting the docker enviroment:


7. Save output:

```
docker> cp OneLeptonMultiJets2018.* atlasNN/
```



