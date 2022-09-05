# go-get-multi

A package used to easily download many files from the web, check their integrity, and write to disk in a specified location


## Config

Configuration for batch downloads look like this. There are 2 levels of configuration, the top level configuration is considered the defaults for all operations, individual download operations can overwrite them.

```json
{
    "config": {
        "create_directories": true,
    },
    "downloads": [
        {
            "target": "/home/iainvm/downloads/go.mod",
            "source": {
                "retriever": "web",
                "location": "https://raw.githubusercontent.com/iainvm/bingo/main/go.mod",
            },
            "hash": "md5:ACBDEFGH",
            "config": {
                "create_directories": false
            }
        },
        {
            "target": "/tmp/README.md",
            "source": {
                "retriever": "web",
                "location": "https://raw.githubusercontent.com/iainvm/bingo/main/go.mod",
            },
            "hash": "md5:ACBDEFGH",
            "config": {
                "create_directories": false,
                "skip_integrity_check": true
            }
        }
    ]
}
```
