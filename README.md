### What
When yaml have quoted keys, schema not works

### Scenario
Edit yaml template generate by `jsonnet`

### Reproduce
- Verify schema works when no quote

Open
```sh
code --goto work/docker-compose.yml:1
```

Verify
```txt
<cursor>version</cursor>: "3.7"

Hint: The version of the Docker Compose document
```

Yes, schema works when no quotes.

- Verify schema NOT work when quoted

Open
```sh
code --goto fail/docker-compose.yml:1
```

Verify
```txt
<cursor>"version"</cursor>: "3.7"

(Nothing...)
```

### Actual
```txt
<cursor>"version"</cursor>: "3.7"

(Nothing...)
```

### Expectd
```txt
<cursor>"version"</cursor>: "3.7"

Hint: The version of the Docker Compose document
```
