# ExRerun

Recompiles mix project on any change to the project src files.

The initial version of this project is inspired by the - currently
unmaintained - `remix` project by AgilionApps:
https://github.com/AgilionApps/remix

## Installation

Install `ex_rerun` by adding it as a dependency to `mix.exs`.

```elixir
def deps do
  [{:ex_rerun, "~> 0.1", only: :dev}]
end
```

## Configuration

It is possible to configure `ex_rerun` using the following parameters:

> Note: the example below shows the default values.

```elixir
config :ex_rerun,
  scan_interval: 4000,
  silent: false,
  elm: false,
  test: false,
  escript: false,
  paths: ["lib", "priv"],
  file_types: [".ex", ".exs", ".eex", ".json"]
```

where:

- `scan_interval` specifies the number of ms to wait between rerun checks,
- `silent` toggles whether to print every time `ex_rerun` recompiles,
- `elm` toggles whether to run the elm compilation task on recompile, requires
  [elm_compile](https://hex.pm/packages/elm_compile) to be installed as a
  project dependency,
- `test` toggles whether to also run mix test after each recompilation,
- `escript` toggles whether to run the escript compilation task on recompile,
- `paths` lists which folders to monitor, and
- `file_types` lists which files that will trigger a rerun when changed.
