# span-batch-research

## Quickstart

To run everything, follow below commands:
```sh
git clone https://github.com/testinprod-io/optimism && cd optimism
# every analysis tool is built on branch: pcw109550/span-batch-tester-with-tx-encoding
git switch pcw109550/span-batch-tester-with-tx-encoding
# ensure we are at correct code
git checkout 46f54d18a664b6b28089ccee75ccc45ec6708738

cd op-node
# every artifacts will be build upon op-node/ directory
ls -al | grep ".ipynb"
# Result:
# -rw-r--r--   1 changwan.park  wheel  675164 Dec 21 15:26 span-batch-analysis.ipynb
# -rw-r--r--   1 changwan.park  wheel   14160 Dec 21 15:26 span-batch-data-preparation.ipynb
# -rw-r--r--   1 changwan.park  wheel  582765 Dec 21 15:26 span-batch-format.ipynb

# all ipynb scripts store result and fetch config/secret from op-node/span-batch-analysis directory
```

You can find below three files at op-node directory:
- `span-batch-data-preparation.ipynb`
- `span-batch-analysis.ipynb`
- `span-batch-format.ipynb`

These are the templates which are mentioned below.

To quick start, first initialize `op-node/span-batch-analysis/secret.yaml`(default gitignored, so you must create your own). This will contain RPC endpoints.

Example content of `secret.yaml`:
```
L1_MAINNET_RPC: http://[SECRET]:8545
L2_OP_MAINNET_RPC: http://[SECRET]:28545
L2_ZORA_MAINNET_RPC: https://rpc.zora.energy
L2_BASE_MAINNET_RPC: https://mainnet.base.org
L2_PGN_MAINNET_RPC: https://rpc.publicgoods.network


L1_GOERLI_RPC: http://[SECRET]:8545
L2_OP_GOERLI_RPC: http://[SECRET]:18545
```

Now open `span-batch-data-preparation.ipynb`, and select your chain. After data preparation is done, run `span-batch-analysis.ipynb` and `span-batch-format.ipynb`. You must specify `l1_chain_name` and `l2_chain_name` for each ipynbs. You may adjust `op-node/span-batch-analysis/config/` content to tweak data collection range.

## Structures and Results

As you can see, below two files are templates.
- `span-batch-data-preparation.ipynb`
- `span-batch-analysis.ipynb`

But below is not.
- `span-batch-format.ipynb`

We can tweak `l1_chain_name`, `l2_chain_name` and analyze for each L2 chain. Example results are stored at this repository: at [span-batch-analysis/results_ipynb](span-batch-analysis/results_ipynb). Results for `span-batch-format.ipynb` is as is, provided in this repository.

You can reproduce results stored at [span-batch-analysis/results_ipynb](span-batch-analysis/results_ipynb) by using the config located in this repository: [span-batch-analysis/config](span-batch-analysis/config). So, you may copy [span-batch-analysis/config](span-batch-analysis/config) into op-node directory and run ipynb templates for reproduction.

### Data Preparation

Template
- [span-batch-data-preparation.ipynb](span-batch-data-preparation.ipynb)

Mainnet
- [span-batch-data-preparation-mainnet-op.ipynb](span-batch-analysis/results_ipynb/span-batch-data-preparation-mainnet-op.ipynb)
- [span-batch-data-preparation-mainnet-base.ipynb](span-batch-analysis/results_ipynb/span-batch-data-preparation-mainnet-base.ipynb)
- [span-batch-data-preparation-mainnet-zora.ipynb](span-batch-analysis/results_ipynb/span-batch-data-preparation-mainnet-zora.ipynb)
- [span-batch-data-preparation-mainnet-pgn.ipynb](span-batch-analysis/results_ipynb/span-batch-data-preparation-mainnet-pgn.ipynb)

Goerli
- [span-batch-data-preparation-goerli-op.ipynb](span-batch-analysis/results_ipynb/span-batch-data-preparation-goerli-op.ipynb)

### Data Analysis

Template
- [span-batch-analysis.ipynb](span-batch-analysis.ipynb)

Mainnet
- [span-batch-analysis-mainnet-op.ipynb](span-batch-analysis/results_ipynb/span-batch-analysis-mainnet-op.ipynb)
- [span-batch-analysis-mainnet-base.ipynb](span-batch-analysis/results_ipynb/span-batch-analysis-mainnet-base.ipynb)
- [span-batch-analysis-mainnet-zora.ipynb](span-batch-analysis/results_ipynb/span-batch-analysis-mainnet-zora.ipynb)
- [span-batch-analysis-mainnet-pgn.ipynb](span-batch-analysis/results_ipynb/span-batch-analysis-mainnet-pgn.ipynb)

Goerli
- [span-batch-analysis-goerli-op.ipynb](span-batch-analysis/results_ipynb/span-batch-analysis-goerli-op.ipynb)

### Data Format

[span-batch-format.ipynb](span-batch-format.ipynb)
