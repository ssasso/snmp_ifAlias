# snmp_ifAlias
SNMP ifAlias script for populating interface description

## Installation
1. Copy `ifAlias_persist` to `/usr/local/bin/ifAlias_persist`, and *chmod +x*
2. Add `pass_persist .1.3.6.1.2.1.31.1.1.1.18 /usr/local/bin/ifAlias_persist` to `/etc/snmp/snmpd.conf`
3. Create the required description files as `/etc/snmp/ifalias/XXX_INTERFACE_XXX.ifalias`
4. Restart `snmpd`

## Testing
You can run: `snmpwalk -v2c -c public 127.0.0.1 ifAlias`. You should obtain sth like:

```
IF-MIB::ifAlias.1 = STRING: Interface lo
IF-MIB::ifAlias.2 = STRING: Interface ens192
IF-MIB::ifAlias.3 = STRING: VPN to XXX
```
