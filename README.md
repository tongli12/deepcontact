# DeepContact

## Installation
1. Install the following dependencies
  - HHBlits 2.0.16
  - Jackhmmer 3.1b2
  - HHFilter 2.0.16
  - CCMPred
  - FreeContact 1.0.21
  - MetaPsicov 1.02
  - Blast 2.2.6
  - Psipred 4.0
2. We need set environment variable `export BLASTDB=/data/work/yang/Qing/databases/data/nr`
3. Modify default.yaml with path to the above programs
4. Install python dependencies with

 ```bash
 conda env create -f environment.yml
 source activate deepcontact-env
 pip install --upgrade https://github.com/Lasagne/Lasagne/archive/master.zip
 ```

## Usage Example

```bash
python data-processing/run_pipeline.py default.yaml test.fasta ./tmp_feature
python deepcontact/feature_gen.py ./deepcontact/feature.yaml ./tmp_feature ./tmp_pickle/feature.pkl
python deepcontact/main.py ./tmp_pickle/feature.pkl ./tmp_output/prediction.pkl
```

