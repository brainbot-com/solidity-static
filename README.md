# DEPRECATED

**Go to https://github.com/ethereum/solidity/releases for versions higher than 0.4.9**

<a href='https://travis-ci.org/brainbot-com/solidity-static'> <img src='https://travis-ci.org/brainbot-com/solidity-static.svg?branch=master'> </a>

#WARNING

This is no official release! Use at your own risk and only if you trust the publisher.


## Static, portable builds of Solidity

This is a script to produce a fully static build of `solc`, the
Solidity compiler.

This is done by statically linking to [musl] in an [Alpine Linux][alpine]
environment. Unlike glibc, musl is built with static linking in
mind.

[musl]: http://www.musl-libc.org/
[alpine]: http://www.alpinelinux.org/

The resulting binary should work on any Linux platform.

```bash
$ file solc soltest
solc: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, stripped
soltest: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, stripped
```

```bash
$ du -h solc soltest
3.0M    solc
5.8M    soltest
```

## Create a release

Use [bumpversion](https://github.com/peritus/bumpversion) to bump version strings to newest upstream version, then push
the newly created commit and tag:

```bash
# Example from 0.4.2 -> 0.4.3
bumpversion patch
git push && git push --tags
```
