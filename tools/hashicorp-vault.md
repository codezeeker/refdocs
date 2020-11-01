Vault

vault operator init \

 -key-shares=3 \

 -key-threshold=2

bash-4.4# vault operator init -key-shares=3 -key-threshold=2

Unseal Key 1: kvumINiPx328r/X/jNMBTxXLkLJxAQO5VgJ6ix90eE34

Unseal Key 2: wp8WMD95Am3XaqkxfKNIyiAMr1BibmHMQo/OstZbBd4J

Unseal Key 3: lzatIYGjdHyrHLZdg9T8+KmQSVTs3e0BnDi6ceqsTdiD

Initial Root Token: f3916478-a4df-0b75-75e4-8711397726e6

curl \

 -H "X-Vault-Token: $VAULT_TOKEN" \

 -H "Content-Type: application/json" \

 -X POST \

 -d '{ "data": { "foo": "world" } }' \

 http://127.0.0.1:8200/v1/secret/data/hello