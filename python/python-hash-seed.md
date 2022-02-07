# Python Hash Seed

Python has a environment flag `PYTHONHASHSEED` that can be set at runtime, but is generally unset in order to defend against "hash-table collision denial of service attacks." Because the hash function used in Python is non-cryptographic, collisions can occur and could be exploited by would-be attackers. Hence the seed was created and usually left random in most situations. However, it is occassionally nice to be able to set the environment flag, for instance when you are wanting to create a reproducible build. See [this blog article](https://vulns.xyz/2021/08/reproducible-python-bytecode) for more details. For those just wondering how to set the flag, setting the flag is easy at runtime or buildtime, and can be set as follows

```bash
PYTHONHASHSEED=<your-choice-seed-int> python3 <program-exec>
```