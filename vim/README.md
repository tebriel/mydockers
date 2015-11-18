# VIM #

example usage:

```sh
docker run -it --rm -v (pwd):/home/user/workdir -v ~/.ssh:/home/user/.ssh tebriel/vim
```

`/home/user/workdir` is where vim opens up, so it expects your files to be
there, map that dir. I use this like I used to use `mvim`. when I'm in a
directory, I run `dvim` which launches a vim docker for editing, which is why i
use `(pwd)`.

Also vim-fugitive is in there, so you'll need your ssh keys if you want to
push/pull. So map that too.

vim-fugutive is broken...try again later
