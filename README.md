# SILK variant of Rocksdb

Note: Don't use this in production. This is just a research prototype.

## Requirements

- Clang and LLVM

## Contributing

Feedback and pull requests welcome!  If a particular feature of RocksDB is 
important to you, please let me know by opening an issue, and I'll 
prioritize it.

## Usage

This binding is statically linked with a specific version of RocksDB. If you 
want to build it yourself, make sure you've also cloned the RocksDB and 
compression submodules:

    git submodule update --init --recursive

## Compression Support
By default, support for the [Snappy](https://github.com/google/snappy), 
[LZ4](https://github.com/lz4/lz4), [Zstd](https://github.com/facebook/zstd), 
[Zlib](https://zlib.net), and [Bzip2](http://www.bzip.org) compression 
is enabled through crate features.  If support for all of these compression 
algorithms is not needed, default features can be disabled and specific 
compression algorithms can be enabled. For example, to enable only LZ4 
compression support, make these changes to your Cargo.toml:

```
[dependencies.rocksdb]
default-features = false
features = ["lz4"]
```
