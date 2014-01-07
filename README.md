libtoml
=======

Fast C parser using Ragel to generate the state machine.

Currently targetted at toml 4f23be43e4 (minus UTF-8)

Usage
=====

```c
#include <toml.h>

struct toml_node *root;
struct toml_node *node;
char *buf = "[foo]\nbar = 1\n";

toml_init(&root);
toml_parse(toml_root, buf, len);

node = toml_get(toml_root, "foo.bar");

toml_dump(toml_root, stdout);
toml_free(root);
```

Building it
===========

```sh
> autoconf
> ./configure
> make
```

If you want to run the tests

```sh
> ./configure --with-cunit=<path_to_cunit>
> make test
> ./test
```

TODO
====

More tests
