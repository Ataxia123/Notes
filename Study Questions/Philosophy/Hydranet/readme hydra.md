```
--- FAIL: TestChangeWalletPasswordNewRootkey (1.63s)
testing.go:1097: TempDir RemoveAll cleanup: unlinkat /tmp/TestChangeWalletPasswordNewRootkey3063283009/001/mainnet: directory not empty
FAIL
FAIL	github.com/lightningnetwork/lnd/walletunlocker	6.171s
FAIL
````")

February 6, 2023 14:08

[watchtower](/hydra-net/vanilla-lnd/tree/master/watchtower "watchtower")

[watchtower/wtdb: add tower-to-session index entry for all towers](/hydra-net/vanilla-lnd/commit/f6ef3db6eae58972750765f02177410b0e6e9d20 "watchtower/wtdb: add tower-to-session index entry for all towers
In this commit, a small migration is added to the watchtower client DB
to ensure that there is an entry in the towerID-to-sessionID index for
all towers in the db regardless of if they have sessions or not. This is
required as a follow up to migration 1 since that migration only created
entries in the index for towers that had associated sessions which would
lead to "tower not found" errors on start up.")

March 8, 2023 11:00

[zpay32](/hydra-net/vanilla-lnd/tree/master/zpay32 "zpay32")

[multi: fix make lint](/hydra-net/vanilla-lnd/commit/84fd911b476240bf6d172b54e734e99e38520c8d "multi: fix make lint
Fixes new lint errors caught by the latest version.")

November 18, 2022 20:48

[.editorconfig](/hydra-net/vanilla-lnd/blob/master/.editorconfig ".editorconfig")

[.editorconfig: add editor settings for most editors](/hydra-net/vanilla-lnd/commit/2681c02afd687960a8323bf725d5f13406dde0e9 ".editorconfig: add editor settings for most editors
This should automatically set the tab size to 8 spaces and add a visual
guide (ruler) at 80 characters in GoLand, GitHub and a few other
editors.")

July 6, 2022 13:33

[.gitignore](/hydra-net/vanilla-lnd/blob/master/.gitignore ".gitignore")

[multi: move `itest` out of `lntest`](/hydra-net/vanilla-lnd/commit/0bc86a3b4bb49b7c5e57152438e19c61edca2e9d "multi: move `itest` out of `lntest`
This commit moves all the test cases living in `itest` out of `lntest`,
further making `lntest` an independent package for general testing.")

February 23, 2023 21:56

[.golangci.yml](/hydra-net/vanilla-lnd/blob/master/.golangci.yml ".golangci.yml")

[golangci: remove linter exceptions for itest](/hydra-net/vanilla-lnd/commit/5bea444b6dada1774e62672680498d8e79002b4e "golangci: remove linter exceptions for itest")

February 23, 2023 21:56

[.travis.yml](/hydra-net/vanilla-lnd/blob/master/.travis.yml ".travis.yml")

[build: bump min Go version to 1.19](/hydra-net/vanilla-lnd/commit/0bbbd9b911e4fd501a18b7f699f53e104e63f3d1 "build: bump min Go version to 1.19
Fixes https://github.com/lightningnetwork/lnd/issues/7495")

March 8, 2023 18:02

[Dockerfile](/hydra-net/vanilla-lnd/blob/master/Dockerfile "Dockerfile")

[build: bump min Go version to 1.19](/hydra-net/vanilla-lnd/commit/0bbbd9b911e4fd501a18b7f699f53e104e63f3d1 "build: bump min Go version to 1.19
Fixes https://github.com/lightningnetwork/lnd/issues/7495")

March 8, 2023 18:02

[LICENSE](/hydra-net/vanilla-lnd/blob/master/LICENSE "LICENSE")

[multi: Update Licenses to 2022 [skip ci]](/hydra-net/vanilla-lnd/commit/62dc1b5323dbf12175146899bb55dfe507a77cd3 "multi: Update Licenses to 2022 [skip ci]")

February 9, 2022 00:25

[Makefile](/hydra-net/vanilla-lnd/blob/master/Makefile "Makefile")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[README.md](/hydra-net/vanilla-lnd/blob/master/README.md "README.md")

[trivial: link from readme to builder's guide](/hydra-net/vanilla-lnd/commit/368fa02543cff1146a6e0c04508ea2003cc015b8 "trivial: link from readme to builder's guide
This PR changes a link in the section Developer Resources from dev.lightning.community (unmaintained) to docs.lightning.engineering.
It also specifies more clearly what readers can expect to find there.")

September 10, 2021 05:42

[SECURITY.md](/hydra-net/vanilla-lnd/blob/master/SECURITY.md "SECURITY.md")

[lnd: add SECURITY.MD to bolster security entry in README](/hydra-net/vanilla-lnd/commit/609cc8b883c7e6186e447e8d7e6349688d78d4fd "lnd: add SECURITY.MD to bolster security entry in README")

October 17, 2022 12:05

[channel_notifier.go](/hydra-net/vanilla-lnd/blob/master/channel_notifier.go "channel_notifier.go")

[multi: use btcd's btcec/v2 and btcutil modules](/hydra-net/vanilla-lnd/commit/7dfe4018ce2f95c2f6a9ff04e370f668fc755138 "multi: use btcd's btcec/v2 and btcutil modules
This commit was previously split into the following parts to ease
review:
- 2d746f68: replace imports
- 4008f0fd: use ecdsa.Signature
- 849e33d1: remove btcec.S256()
- b8f6ebbd: use v2 library correctly
- fa80bca9: bump go modules")

March 9, 2022 19:02

[chanrestore.go](/hydra-net/vanilla-lnd/blob/master/chanrestore.go "chanrestore.go")

[channeldb: BigSize migration, store zero-conf, scid-alias bits](/hydra-net/vanilla-lnd/commit/c9f591260121ed4bc896ac09f6505147ef93f8ab "channeldb: BigSize migration, store zero-conf, scid-alias bits
This introduces a BigSize migration that is used to expand the width
of the ChannelStatus and ChannelType fields. Three channel "types"
are added - ZeroConfBit, ScidAliasChanBit, and ScidAliasFeatureBit.
ScidAliasChanBit denotes that the scid-alias channel type was
negotiated for the channel. ScidAliasFeatureBit denotes that the
scid-alias feature bit was negotiated during the *lifetime* of the
channel. Several helper functions on the OpenChannel struct are
exposed to aid callers from different packages.
The RefreshShortChanID has been renamed to Refresh.
A new function BroadcastHeight is used to guard access to the
mutable FundingBroadcastHeight member. This prevents data races.")

July 7, 2022 17:10

[config.go](/hydra-net/vanilla-lnd/blob/master/config.go "config.go")

[Merge pull request](/hydra-net/vanilla-lnd/commit/f4fdd82327af8e437afd343b577977c58ff0394f "Merge pull request #7264 from yyforyongyu/gossip-resend-messages
discovery: fix message order in batch sending") [lightningnetwork#7264](https://github.com/lightningnetwork/lnd/pull/7264) [from yyforyongyu/gossip-rese…](/hydra-net/vanilla-lnd/commit/f4fdd82327af8e437afd343b577977c58ff0394f "Merge pull request #7264 from yyforyongyu/gossip-resend-messages
discovery: fix message order in batch sending")

February 21, 2023 17:10

[config_builder.go](/hydra-net/vanilla-lnd/blob/master/config_builder.go "config_builder.go")

[multi: make linter happy](/hydra-net/vanilla-lnd/commit/4a0a15586b28f5e82bf4977fe77855558a152b7d "multi: make linter happy
Fix all the linter problems for the `v0.16.0-beta.rc3`.")

March 11, 2023 23:29

[dev.Dockerfile](/hydra-net/vanilla-lnd/blob/master/dev.Dockerfile "dev.Dockerfile")

[build: bump min Go version to 1.19](/hydra-net/vanilla-lnd/commit/0bbbd9b911e4fd501a18b7f699f53e104e63f3d1 "build: bump min Go version to 1.19
Fixes https://github.com/lightningnetwork/lnd/issues/7495")

March 8, 2023 18:02

[doc.go](/hydra-net/vanilla-lnd/blob/master/doc.go "doc.go")

[lnd: rename package main->lnd](/hydra-net/vanilla-lnd/commit/b53899c43caa3697b553c6f11b361e1eff65aade "lnd: rename package main->lnd")

April 23, 2019 20:57

[go.mod](/hydra-net/vanilla-lnd/blob/master/go.mod "go.mod")

[build: bump min Go version to 1.19](/hydra-net/vanilla-lnd/commit/0bbbd9b911e4fd501a18b7f699f53e104e63f3d1 "build: bump min Go version to 1.19
Fixes https://github.com/lightningnetwork/lnd/issues/7495")

March 8, 2023 18:02

[go.sum](/hydra-net/vanilla-lnd/blob/master/go.sum "go.sum")

[mod: bump neutrino lru cache version](/hydra-net/vanilla-lnd/commit/52facd3e5a3f457c75a296d1f48329469931773d "mod: bump neutrino lru cache version")

March 3, 2023 14:43

[intercepted_forward.go](/hydra-net/vanilla-lnd/blob/master/intercepted_forward.go "intercepted_forward.go")

[contractcourt: add onchain interception](/hydra-net/vanilla-lnd/commit/721fb4ee8878f53a3440ac872130f7ce31c49c3d "contractcourt: add onchain interception")

April 13, 2022 11:31

[lnd.go](/hydra-net/vanilla-lnd/blob/master/lnd.go "lnd.go")

[lnd: Add ability to encrypt TLS key on disk](/hydra-net/vanilla-lnd/commit/c0f44a17b75784f018652cb382c6ef4cd34d7ae0 "lnd: Add ability to encrypt TLS key on disk")

January 26, 2023 13:32

[log.go](/hydra-net/vanilla-lnd/blob/master/log.go "log.go")

[multi: add sub-server dep](/hydra-net/vanilla-lnd/commit/635cffa8718d4b9fadb6269a5c15b834dc857d4a "multi: add sub-server dep")

April 30, 2022 08:55

[logo.png](/hydra-net/vanilla-lnd/blob/master/logo.png "logo.png")

[README: add logo to top portion of page](/hydra-net/vanilla-lnd/commit/fba856068e95bccf31f443a355c853b7f19bc11c "README: add logo to top portion of page")

September 29, 2017 14:06

[pilot.go](/hydra-net/vanilla-lnd/blob/master/pilot.go "pilot.go")

[multi: use btcd's btcec/v2 and btcutil modules](/hydra-net/vanilla-lnd/commit/7dfe4018ce2f95c2f6a9ff04e370f668fc755138 "multi: use btcd's btcec/v2 and btcutil modules
This commit was previously split into the following parts to ease
review:
- 2d746f68: replace imports
- 4008f0fd: use ecdsa.Signature
- 849e33d1: remove btcec.S256()
- b8f6ebbd: use v2 library correctly
- fa80bca9: bump go modules")

March 9, 2022 19:02

[rpcserver.go](/hydra-net/vanilla-lnd/blob/master/rpcserver.go "rpcserver.go")

[rpcserver: assign peer alias lookup error](/hydra-net/vanilla-lnd/commit/213bdb2e0115798b135689d8956cf59550372a28 "rpcserver: assign peer alias lookup error")

March 3, 2023 10:07

[rpcserver_test.go](/hydra-net/vanilla-lnd/blob/master/rpcserver_test.go "rpcserver_test.go")

[Rpcserver: Add GetAllPermissions function for retrieving permissions …](/hydra-net/vanilla-lnd/commit/218fa1e43e21d4d7ac780df99d981f5be0ba6b42 "Rpcserver: Add GetAllPermissions function for retrieving permissions for external macaroon baking")

October 1, 2021 16:51

[sample-lnd.conf](/hydra-net/vanilla-lnd/blob/master/sample-lnd.conf "sample-lnd.conf")

[routing+lnrpc: make capacity factor configurable](/hydra-net/vanilla-lnd/commit/a73581610e1c23f0e18aa7be29047b7af74f0630 "routing+lnrpc: make capacity factor configurable
We make the capacity factor configurable via an lnd.conf routerrpc
apriori parameter. The capacity factor trades off increased success
probability with a reduced set of channel candidates, which may lead to
increased fees. To let users choose whether the factor is active or not,
we add a config setting where a capacity fraction of 1.0 disables the
factor. We limit the capacity fraction to values between 0.75 and 1.0.
Lower values may discard too many channels.")

February 24, 2023 15:28

[server.go](/hydra-net/vanilla-lnd/blob/master/server.go "server.go")

[discovery+server: add more trace log](/hydra-net/vanilla-lnd/commit/f22b25a1bf0382e18003db1eef8b5b803b578562 "discovery+server: add more trace log")

March 8, 2023 21:02

[server_test.go](/hydra-net/vanilla-lnd/blob/master/server_test.go "server_test.go")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[subrpcserver_config.go](/hydra-net/vanilla-lnd/blob/master/subrpcserver_config.go "subrpcserver_config.go")

[chainrpc: add chainkit RPC service](/hydra-net/vanilla-lnd/commit/561bf829857a51c1d1c2f6fea18eac8d6726143e "chainrpc: add chainkit RPC service
New endpoints: GetBlock, GetBestBlock, and GetBlockHash.")

December 7, 2022 14:50

[tls_manager.go](/hydra-net/vanilla-lnd/blob/master/tls_manager.go "tls_manager.go")

[lnd: bump lnd/cert version](/hydra-net/vanilla-lnd/commit/91af62a031060751840b0a01032c395c6ad1c7b9 "lnd: bump lnd/cert version
This commit bumps the lnd/cert version to 1.2.1 and fixes all call sites
where cert.GenCertPair was called.")

February 7, 2023 09:50

[tls_manager_test.go](/hydra-net/vanilla-lnd/blob/master/tls_manager_test.go "tls_manager_test.go")

[lnd: Add ability to encrypt TLS key on disk](/hydra-net/vanilla-lnd/commit/c0f44a17b75784f018652cb382c6ef4cd34d7ae0 "lnd: Add ability to encrypt TLS key on disk")

January 26, 2023 13:32

[witness_beacon.go](/hydra-net/vanilla-lnd/blob/master/witness_beacon.go "witness_beacon.go")

[multi: create channeldb/models package](/hydra-net/vanilla-lnd/commit/383cb40f8d2352e80657e7a185f115e9a9f4e74a "multi: create channeldb/models package
Add a new subpackage to `lnd/channeldb` to hold some of the types that
are used in the package itself and in other packages that should not
depend on `channeldb`.")

January 16, 2023 07:14

[witness_beacon_test.go](/hydra-net/vanilla-lnd/blob/master/witness_beacon_test.go "witness_beacon_test.go")

[lnd: replace defer cleanup with `t.Cleanup`](/hydra-net/vanilla-lnd/commit/604a355db6f1219647f9d9cb7c5378dcbda445be "lnd: replace defer cleanup with `t.Cleanup`
Signed-off-by: Eng Zer Jun <engzerjun@gmail.com>")

October 13, 2022 17:47

View code￼￼Sign In Required

Please ￼￼sign in￼￼￼￼￼￼￼￼ to use Codespaces.

​￼￼￼Launching GitHub Desktop

If nothing happens, ￼￼download GitHub Desktop￼￼￼￼￼￼￼￼￼ and try again.

​￼￼￼Launching GitHub Desktop

If nothing happens, ￼￼download GitHub Desktop￼￼￼￼￼￼￼￼￼ and try again.
[Skip to content](#start-of-content)

Toggle navigation

[](https://github.com/)

[Sign up](/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F%3Cuser-name%3E%2F%3Crepo-name%3E&source=header-repo)

​￼- Product
    
    ​￼- [
        
        Actions
        
        Automate any workflow
        
        ](/features/actions)
    ​￼- [
        
        Packages
        
        Host and manage packages
        
        ](/features/packages)
    ​￼- [
        
        Security
        
        Find and fix vulnerabilities
        
        ](/features/security)
    ​￼- [
        
        Codespaces
        
        Instant dev environments
        
        ](/features/codespaces)
    ​￼- [
        
        Copilot
        
        Write better code with AI
        
        ](/features/copilot)
    ​￼- [
        
        Code review
        
        Manage code changes
        
        ](/features/code-review)
    ​￼- [
        
        Issues
        
        Plan and track work
        
        ](/features/issues)
    ​￼- [
        
        Discussions
        
        Collaborate outside of code
        
        ](/features/discussions)
    
    Explore
    
    - ￼￼All features￼￼￼￼￼￼￼￼
    - ￼￼Documentation￼￼￼￼￼￼￼￼￼
    - ￼￼GitHub Skills￼￼￼￼￼￼￼￼￼
    - ￼￼Blog￼￼￼￼￼￼￼￼￼
    
​￼- Solutions
    
    For
    
    - ￼￼Enterprise￼￼￼￼￼￼￼￼
    - ￼￼Teams￼￼￼￼￼￼￼￼
    - ￼￼Startups￼￼￼￼￼￼￼￼
    - ￼￼Education￼￼￼￼￼￼￼￼￼
    
    By Solution
    
    - ￼￼CI/CD & Automation￼￼￼￼￼￼￼￼
Search or jump to...
​￼￼￼Launching Xcode

If nothing happens, ￼￼download Xcode￼￼￼￼￼￼￼￼￼ and try again.

​￼￼￼Launching Visual Studio Code

Your codespace will open once ready.

There was a problem preparing your codespace, please try again.

This branch is ￼￼782 commits behind￼￼￼￼￼￼￼￼￼ lightningnetwork:master.

[[Latest commit hydra]]

￼￼Git stats hydra￼￼


[[Want some Sass with your obsidian theme‽ here's How and Why]]