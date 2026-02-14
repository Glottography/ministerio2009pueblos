# Releasing the dataset

## Recreate the raw data from glottography-data

In case of upstream changes in glottography-data:
```shell
cldfbench download cldfbench_ministerio2009pueblos.py
```

## Recreate the CLDF data

```shell
cldfbench makecldf cldfbench_ministerio2009pueblos.py --glottolog-version v5.2
cldfbench cldfreadme cldfbench_ministerio2009pueblos.py
cldfbench zenodo --communities glottography cldfbench_ministerio2009pueblos.py
cldfbench readme cldfbench_ministerio2009pueblos.py
```

## Validation

```shell
cldf validate cldf
```

```shell
cldfbench geojson.validate cldf
25      valid features
21      valid speaker areas
```

```shell
cldfbench geojson.glottolog_distance cldf --format pipe
```

| ID | Distance | Contained | NPolys |
|:---------|-----------:|:------------|---------:|
| alle1238 | 0.43 | False | 1 |
| calc1235 | 0.00 | False | 2 |
| char1240 | 3.83 | False | 1 |
| kunz1244 | 1.66 | False | 1 |
| lule1238 | 0.72 | False | 1 |
| mbya1239 | 0.93 | False | 2 |
| moco1246 | 0.00 | True | 1 |
| onaa1245 | 0.60 | False | 1 |
| pila1245 | 0.00 | False | 1 |
| puel1244 | 5.46 | False | 3 |
| tehu1242 | 0.00 | False | 4 |
| wich1264 | 0.00 | True | 1 |


## Release

Commit and push all changes.

Run
```
cldfbench glottography.release cldfbench_ministerio2009pueblos.py vX.Y
```
and follow the instructions given in the output of the command.
