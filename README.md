# Example BinSync Project
An example BinSync project for testing and validation

## BinSync Project Format
A BinSync project is a directory (folder) that is a Git project and conatins at least 2 things:
1. a `binsync/root` branch
2. a `binay_hash`: a md5 hash of the thing you are reversing (in that root branch)

After this every branch starting with `binsync/` is a User branch containg user artifact changes.
Each branch layout will look something like this depending on what the user has worked on:
```tree
.
├── structs
│   └── mahaloz_struct.toml
├── patches.toml
├── metadata.toml
├── global_vars.toml
├── functions
│   └── 0040071d.toml
├── enums.toml
├── comments.toml
└── binary_hash
```

Each toml describes the changes the user has made as well as timestamps and commits. 
A good example branch to look at is the [binsync/mahaloz](https://github.com/binsync/example.bsproj/tree/binsync/mahaloz) branch which contains a few changes in functions and structs.


## Good practice
- put the binary people are reversing in the `main` branch or any non `binsync/` branch, since that file may be copied
- ALWAYS when you work on the binary in your decompiler, first copy it out of here so files like ida files dont polute the repo
