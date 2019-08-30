## Generate Bitcoin Core BIP32 addresses

```python
# create_btc_wallet.py

from pywallet import wallet

# generate 12 word mnemonic seed
seed = wallet.generate_mnemonic()
print(seed)

# create bitcoin wallet
wallet = wallet.create_wallet(network="BTC", seed=seed, path="m/0'/0'", num=1000000, hardened=True)

print("xpub: ", wallet["xpublic_key"])
print("xprv: ",  wallet["xprivate_key"])
print("path: ", wallet["path"])

for x in wallet["addresses"]:
    print(x)
```
