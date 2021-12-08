```bash
[alias]
	st = status
	ps = push
	a = add
	d = diff --staged
	co = checkout
	br = branch
	rt = remote
	pl = pull
	ft = fetch
	mr = merge
    tg = tag
	lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --stat
	rank = shortlog -sn --no-merges
	cm = commit
	conf = config --list
	pure = pull --rebase
	del = restore --staged
```