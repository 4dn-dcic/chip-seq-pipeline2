Dev
===

## Building templates on DX for each genome

Make sure that you have [`dxWDL-0.77.jar`](https://github.com/dnanexus/dxWDL/releases/download/0.77/dxWDL-0.77.jar) on your `$HOME`. Install [DNANexus Platform SDK](https://wiki.dnanexus.com/downloads) with `pip install dxpy`. Log-in on DNANexus with `dx login` and choose "ENCODE Uniform Processing Pipelines" (name of our official DNANexus project for pipelines).

Run the following command line locally to build out DX workflows for this pipeline on our official one. This will overwrite (`-f` parameter does it).

```
# version
VER=v1.1.1

# general
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/general -defaults examples/dx/template_general.json

# hg38
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/hg38 -defaults examples/dx/template_hg38.json

# hg19
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/hg19 -defaults examples/dx/template_hg19.json

# mm10
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/mm10 -defaults examples/dx/template_mm10.json

# mm9
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/mm9 -defaults examples/dx/template_mm9.json

# test sample
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/test_ENCSR936XTK_subsampled -defaults examples/dx/ENCSR936XTK_subsampled_dx.json
```

## DX Azure
```
# version
VER=v1.1.1

# general
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines Azure" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/general -defaults examples/dx_azure/template_general.json

# hg38
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines Azure" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/hg38 -defaults examples/dx_azure/template_hg38.json

# hg19
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines Azure" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/hg19 -defaults examples/dx_azure/template_hg19.json

# mm10
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines Azure" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/mm10 -defaults examples/dx_azure/template_mm10.json

# mm9
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines Azure" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/mm9 -defaults examples/dx_azure/template_mm9.json

# test sample
java -jar ~/dxWDL-0.77.jar compile chip.wdl -project "ENCODE Uniform Processing Pipelines Azure" -extras workflow_opts/docker.json -f -folder /ChIP-seq2/workflows/$VER/test_ENCSR936XTK_subsampled -defaults examples/dx_azure/ENCSR936XTK_subsampled_dx_azure.json
```