# replace-vercel-dns-records

A GitHub action for replacing Vercel DNS records.

Takes the following required arguments:

- domain: the vercel domain, e.g. `uniswap.org`
- subdomain: the subdomain, e.g. `_dnslink.app`
- record-type: the record type, e.g. `TXT`
- value: the value to use for the record, e.g. `dnslink=/ipfs/Qm...`
- token: the vercel token to use, should be a github secret
- team-name: the name of the team that owns the domain, e.g. `uniswap`

Example usage:

```yaml
- name: Update DNS with new IPFS hash
  uses: uniswap/replace-vercel-dns-records@v1.0.0
  with:
    domain: 'uniswap.org'
    subdomain: '_dnslink.app'
    record-type: 'TXT'
    value: dnslink=/ipfs/${{ steps.upload.outputs.hash }}
    token: ${{ secrets.VERCEL_TOKEN }}
    team-name: 'uniswap'
```
