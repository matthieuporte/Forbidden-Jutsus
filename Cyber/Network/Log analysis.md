
Useful commands for getting precise information in a text file :

- `cat`
- `more`
- `less`
- `head`
- `tail`
- `wc`
- `nl`
- `cut`

### Example :
```shell
cat access.log
```

```plaintext
[2023/10/25:15:42:02] 10.10.120.75 sway.com:443 CONNECT - 200 0 "-" 
[2023/10/25:15:42:02] 10.10.120.75 sway.com:443 GET / 301 492 "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/118.0.0.0 Safari/537.36" 
--- REDACTED FOR BREVITY ---
```

The command :

```shell
cut -d ' ' -f1,3,6 access.log | head -n 1
```

show only the first line with only the 1st, 3rd and 6th element