# ssh-toolkit

`sshkit`: aliases, connect, run, push/pull, tunnel, key copy, health check. One bash file, no deps.

Everything reads your normal `~/.ssh/config` (or `$SSHKIT_CONFIG`), so plain `ssh web` keeps working alongside it.

## Runbook

```bash
curl -fsSL https://raw.githubusercontent.com/coffeestained/ssh-toolkit/main/sshkit -o ~/.local/bin/sshkit && chmod +x ~/.local/bin/sshkit

sshkit add web deploy@203.0.113.10:22 -i ~/.ssh/web.key
sshkit key web                          # install your public key
sshkit check web                        # ok?
sshkit go web                           # shell
sshkit run web 'df -h /'                # one-off command
sshkit push web ./dist /var/www/app/    # rsync up (scp fallback)
sshkit pull web /var/log/nginx ./logs   # rsync down
sshkit tunnel web 5432                  # localhost:5432 -> remote 5432 (ctrl-c closes)
sshkit tunnel web 27017:db.internal:27017
sshkit ls && sshkit rm web
```

## Files

| file | purpose |
|---|---|
| `sshkit` | the tool; `sshkit` with no args prints usage |
| `config.example` | what `sshkit add` writes, for hand-editing |

MIT © Matthew Grady
