# How it works
The code generates the SORAv1 address, public key and migration signature based on 12 words mnemonic or private key.
The signature is ecnrypt(SHA3(SORAv1 address + SORAv1 public key)).

# How to build
```shell
cd sora-migration
./gradlew jar
```
# How to run

```shell
cd build/libs
java -jar sora-migration-1.0.0 jar "<mnemonic>" <iroha_address>
```
The `<mnemonic>` should be replaced with SORAv1 mnemonic.

The `<iroha_address>` is optional. This parameter should be used if address doesn't match `did_*******@sora` format. The example is `sora@sora`

Or 
```shell
cd build/libs
java -jar sora-migration-1.0.0 jar <private key> <iroha_address>
```
The `<private key>` should be replaced with SORAv1 private key without `0x` in the beginning.

The `<iroha_address>` is optional. This parameter should be used if address doesn't match `did_*******@sora` format. The example is `sora@sora`

The example of the output
```shell
iroha_address did_sora_3e26d04d4d0afb5bf008@sora
iroha_public_key 3e26d04d4d0afb5bf0088128e148ea75d0b4da7179d80ec1845567b5614e2ccf
iroha_signature 35868560affa53be39bbe09a67e593d09c3420edda9230fa06b612cddd1369b9e62bfb827b34054a7a7e2eab7aad43cb228c97c76efba3fc65f8767d5cb4cf03

```
