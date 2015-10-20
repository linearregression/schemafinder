# Prerequisities #

  * [combonodefinder](http://code.google.com/p/nodefinder) installed.
  * [schemafinder](http://code.google.com/p/schemafinder/wiki/InstallHowto) installed.

# Example #

In one OS shell type:
```
shell% erl -name one -setcookie yum
Erlang (BEAM) emulator version 5.6.5 [source] [async-threads:0] [kernel-poll:false]

Eshell V5.6.5  (abort with ^G)
(one@ub32vmwsrv.localdomain)1> schemafinder:start ().
ok
```

Leave that open.  In another OS shell type:
```
another% erl -name two -setcookie yum
Erlang (BEAM) emulator version 5.6.5 [source] [async-threads:0] [kernel-poll:false]

Eshell V5.6.5  (abort with ^G)
(two@ub32vmwsrv.localdomain)1> schemafinder:start ().
ok
(two@ub32vmwsrv.localdomain)2> mnesia:system_info (db_nodes).
['two@ub32vmwsrv.localdomain','one@ub32vmwsrv.localdomain']
```

Now you have two Erlang VMs running mnesia in distributed mode with a single distributed schema.

'nuff said.