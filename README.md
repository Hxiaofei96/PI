# PI LIBRARY REPOSITORY

See [examples] (examples/) for how to use the PI.

## Dependencies

- libjudy-dev
- libreadline-dev

## PI CLI

For now the PI CLI supports an experimental version of `table_add` and
`table_delete`. Because these two functions have been implemented in the bmv2 PI
implementation, you can test the PI CLI with the bmv2 `simple_switch`. Assuming
bmv2 is installed on your system, build the PI and the CLI with `./configure
--with-bmv2 && make`. You can then experiment with the following commands:

    simple_switch tests/testdata/simple_router.json  // to start the switch
    ./CLI/pi_CLI_bmv2 tests/testdata/simple_router.json  // to start the CLI
    PI CLI> select_device 0 port=9090
    PI CLI> table_add ipv4_lpm set_nhop 10.0.0.1/24 => 10.0.0.1 1
    PI CLI> table_dump ipv4_lpm
    PI CLI> table_delete ipv4_lpm <handle returned by table_add>
