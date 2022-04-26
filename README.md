# James O'Beirne CTV vault using ANYPREVOUT in place of CTV

## About

This is a fork of [jamesob/simple-ctv-vault](https://github.com/jamesob/simple-ctv-vault).
Please refer to this repo for any information about the scheme.

See [this commit](https://github.com/darosior/simple-anyprevout-vault/commit/d258817657a9859eabf3732c94edc62c83100fea) for the logic specific to replacing CTV with an ANYPREVOUTANYSCRIPT signature.
See the master branch's commits for the whole diff which contains:
1. An adaptation of the Scripts to Taproot
2. A drop-in replacement of using an APO-AS signature in place of a CTV
3. A cleanup removing the CTV-specific stuff


## Demo

```sh
$ git clone https://github.com/darosior/simple-anyprevout-vault
$ cd simple-anyprevout-vault
$ pip install -r requirements.txt

# build the ANYPREVOUT implementation in Bitcoin Core
#  https://github.com/remyers/bitcoin/commits/202101-anyprevout
$ bitcoind -regtest -txindex=1 &

# Run the functional tests, the easiest way to exercise the two paths
$ pip install pytest && pytest
```

## Credits

James for the original vault implem, i only converted it to use ANYPREVOUT.
Richard Myers, i stole some snippets from his APO covenant branch
https://github.com/remyers/bitcoin/commits/covenant-anyprevout.
