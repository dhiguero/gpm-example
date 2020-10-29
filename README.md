# gpm-example

A repository with the reference layout for generating protos with [GPM](https://github.com/dhiguero/grpc-proto-manager).

## Structure

The basic structure expected by the grpc-proto-manager is a simple set of directories from the project root, each of them containing a set of `.proto` files. Optionally, you may specify a `.protolangs` file with the target languages for the generation.

```
├── | <high-level-entity>
│   ├── [.protolangs]
│   └── myprotofile.proto
```

## GPM YAML

To specify how the generation should be done, GPM expects a `.gpm.yaml` at the root project level. The contents of this file are as follows:

```
tempPath: /tmp/gpm
repositoryProvider: github
repositoryOrganization: dhiguero
defaultLanguage: go
```

Where:

* **tempPath**: Specifies the path of a temporal directory used to create intermediate code.
* **repositoryProvider**: Selects the type of repository interface.
* **repositoryOrganization**: Selects the the target organization in the repository provider. In the example, it translates into the generated code being pushed to `github.com/dhiguero/grpc-<high-level-entity>-<language>`.
* **defaultLanguage**: Defines the target language if the `.protolangs` file is not found. 

For further information check the YAML format on [GPM](https://github.com/dhiguero/grpc-proto-manager).