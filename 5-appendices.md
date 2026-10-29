# 5 Appendices

## A Assumptions and dependencies

- Peers behave as Bitcoin Core: they answer `getheaders` as described in
  [3.8](3-requirements/3.8-supporting-information.md#how-a-peer-answers-getheaders), serve blocks with witness data
  for `MSG_WITNESS_BLOCK`, and answer `ping` with `pong` (BIP31).
- Configured peers are reachable and trusted (NET-04).
- rust-bitcoin [R15] provides the network parameters, including deployment heights, for `main`, `testnet4`, `signet`
  and `regtest` (CHN-04).
- `bitcoin-p2p-messages` [R16] provides the message types and transport v1 framing for every command of
  [Table 3.1-1](3-requirements/3.1-external-interfaces.md#311-peer-to-peer-interface).
- The Bitcoin Core script verification bindings [R17] implement the script rules of the Bitcoin Core version in [R3].

## B Acronyms and abbreviations

| Term  | Meaning                                                   |
|-------|-----------------------------------------------------------|
| BIP   | Bitcoin Improvement Proposal                              |
| CRUD  | Create, read, update, delete                              |
| IBD   | Initial block download                                    |
| LCA   | Last common ancestor                                      |
| MTP   | Median time past                                          |
| P2P   | Peer-to-peer                                              |
| P2SH  | Pay to script hash                                        |
| PoW   | Proof of work                                             |
| SRS   | Software Requirements Specification                       |
| TBD   | To be determined                                          |
| TOML  | Tom's Obvious, Minimal Language (configuration format)    |
| UTXO  | Unspent transaction output                                |

## C TBD register

| Id     | Item                                                                                                       | Where                                                                                         |
|--------|------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| TBD-01 | Lifecycle: start-up and shutdown of the node and of its modules.                                           | [3.7 Lifecycle](3-requirements/3.7-system-attributes.md#lifecycle)                            |
| TBD-02 | Connection flow: commands and payloads of the features and tip exchanges; failed or incomplete flow.       | NET-06, [Table 3.1-1](3-requirements/3.1-external-interfaces.md#311-peer-to-peer-interface), [routing table](3-requirements/3.2.1-net.md#routing-table) |
| TBD-03 | Time after which a missing `pong` disconnects the peer.                                                    | NET-10                                                                                        |
| TBD-04 | How `block-sync` is launched and how it switches from IBD to Standard mode.                                | BSY-11                                                                                        |
| TBD-05 | Number of blocks per `getdata` request.                                                                    | BSY-17                                                                                        |
| TBD-06 | Keys of the `[block-sync]` configuration table.                                                            | BSY-29                                                                                        |
| TBD-07 | Bitcoin Core reference version.                                                                            | [R3](2-references.md)                                                                         |
| TBD-08 | Reaction to an invalid message (wrong magic, bad checksum, payload too long).                              | EXT-04                                                                                        |
| TBD-09 | Handling of received `getheaders`, `getdata` and `notfound`.                                               | [Table 3.1-1](3-requirements/3.1-external-interfaces.md#311-peer-to-peer-interface)           |
| TBD-10 | Request timeouts in `block-sync`.                                                                          | BSY-02                                                                                        |
| TBD-11 | Arguments of `add_peer`; result of `send`, `connect`, `disconnect` for a peer in another state.            | NET-18, NET-19                                                                                |
| TBD-12 | Handling of a `rejected` result of `validate_headers` in IBD and in standard mode.                         | BSY-16, BSY-21                                                                                |
