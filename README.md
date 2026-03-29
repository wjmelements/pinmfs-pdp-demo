# TippyFS

## packages/

These submodules pin the version I used to run the demo.

## Demonstration

1. Setup filecoin-pin pinning server with a session key and bearer token auth
2. Use kubo+(fuse3/osxfuse/macfuse) to `ipfs daemon --mount` an MFS folder, configured to use your filecoin-pin pinning server
3. Copy files into the MFS folder
4. pinmfs detects the files and sends /pin request to filecoin-pin pinning server
5. filecoin-pin fetches the file and dir from IPFS using js-libp2p
6. filecoin-pin uploads the content to a PDP storage provider using synapse-sdk
7. The PDP storage provider completes addPieces

## Related Pull Requests

I worked through many issues along the way.

1. [Kubo: Use seaweedfs/fuse for macFUSE](https://github.com/ipfs/kubo/pull/11249)
2. [Synapse SDK: remove powerless DeleteDataSet permission](https://github.com/FilOzone/synapse-sdk/pull/694)
3. [Synapse SDK: helpful error message when rejecting session key](https://github.com/filecoin-project/filecoin-pin/pull/375)
4. [Filecoin Pin: add support for session keys to pinning server](https://github.com/filecoin-project/filecoin-pin/pull/376)
5. [Filecoin Pin: actually check the bearer token](https://github.com/filecoin-project/filecoin-pin/pull/382)
6. [Kubo: Support FUSE3, fix deadlock, attrs, caching](https://github.com/ipfs/kubo/pull/11255)
7. [libp2p: fix StreamStateError](https://github.com/libp2p/js-libp2p/pull/3423)
8. [Filecoin Pin: fix identify flow when there are too many dial options](https://github.com/filecoin-project/filecoin-pin/pull/386)
9. [Kubo: fix gofmt help message](https://github.com/ipfs/kubo/pull/11256)
