# SSB  performance notes

## Testing validation + db query

Performance numbers on the following: 
staltz (@QlCTpvY7p9ty2yOFrv1WU1AE88aoQc4Y7wYal7PFc+w=.ed25519): 7853 messages

```
db2 pullstream query all: 2.405s
3.25 entries per ms

db2 toCallback query all: 1.196s
6.5 entries per ms
```

https://github.com/ssb-ngi-pointer/jitdb/issues/189

```
json encode: 71.463ms
json decode: 70.971ms

rust-validate2: 471ms
validate2: 1.382s
validate:  1.228s

validate without signature: 326.642ms
validate signature no clone + delete: 1.252s
validate 1 buffer of all: 134.165ms
```

## Testing shs

Performance numbers on the following:
arj (@6CAxOI3f+LUOVrbAl0IemqiS7ATpQvr9Mdw9LC4+Uv0=.ed25519) 7797

```
local test query: 600ms
muxrpc with shs:  891ms
```
----

## Testing index creation

> 1mill messages

```
empty db & query for single author: 45   sec
without base & keys level index:    26.5 sec
without decrypt:                    13.6 sec
```
