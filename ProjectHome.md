Schemafinder starts up the local [Mnesia](http://www.erlang.org/doc/apps/mnesia/index.html) and joins a schema defined
at other nodes as discovered by the indicated [nodefinder](http://code.google.com/p/nodefinder) strategy and
the indicated schemafinder group.   It also provides a mechanism for
identifying and pruning mnesia nodes that are permanantly out of service.
Finally it allows optional reuse of the Mnesia directory during shutdown
and guards against joining with a stale schema after
having been removed (which, if not guarded against, leads to undefined
behavior).

Combined these capabilities greatly ease administration and maintenance of Mnesia in a dynamic environment such as [EC2](http://www.amazon.com/gp/browse.html?node=201590011).

Unfortunately, schemafinder currently does not assist in [recovering from networking partitioning](http://www.erlang.org/doc/apps/mnesia/Mnesia_chap7.html#6.7).

Another [Dukes of Erl](http://dukesoferl.blogspot.com) release.