# Common use linux commands for cyber security

## Merge files
```bash
cat *.txt > merge_file
```

## Use line by line in file as cli variable
```bash
cat input_file | xargs -I % sh -c 'command1 %; command2 %; command3 %;'
```

## File scanner per domain
```bash
cat targets-all.txt | xargs -I @ sh -c 'curl -L -m 2 -s -o /dev/null -w "@/.git: contentType: %{content_type} code:%{http_code}\n" @/.git >> ext-search.txt'
```

## Status code test
```bash
cat targets-all.txt | xargs -I @ sh -c 'curl -L -m 2 -s -o /dev/null -w "[%{http_code}]@\n" @ >> domain-status-code.txt'
```

## Extract test subjests

```bash
cat domain-status-code.txt | grep 200 > subjects.txt
```


Feel free to contribute <3
