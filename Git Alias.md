```bash
[alias]
	st = status
	ps = push
	a = add
	d = diff --staged
	co = checkout
	cob = co -b
	br = branch
	bra = br -a
	rt = remote
	pl = pull
	ft = fetch
	mr = merge
	tg = tag
	lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --stat
	rflg = reflog
	rank = shortlog -sn --no-merges
	cm = commit
	cmm = cm -m
	cma = cm --amend -m
	conf = config --list
	pure = pull --rebase
	del = restore --staged
	last = log -1 HEAD
	unstage = reset HEAD --
```