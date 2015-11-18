FROM debian:sid

MAINTAINER Chris Moultrie <chris@moultrie.org>

RUN groupadd -g 1000 user \
	&& useradd --create-home -d /home/user -g user -u 1000 user

RUN apt-get update && apt-get install -y \
        git \
        silversearcher-ag \
        build-essential \
        cmake \
        python \
        python-dev \
        vim-nox \
        ctags \
        vim-doc \
        vim-scripts

USER user
ENV HOME /home/user
ENV TERM xterm-256color

COPY .vimrc $HOME/.vimrc

RUN git clone --recursive https://github.com/kien/ctrlp.vim $HOME/.vim/bundle/ctrlp.vim
RUN git clone --recursive https://github.com/tpope/vim-commentary $HOME/.vim/bundle/vim-commentary
RUN git clone --recursive https://github.com/tpope/vim-markdown $HOME/.vim/bundle/vim-markdown
RUN git clone --recursive https://github.com/groenewege/vim-less $HOME/.vim/bundle/vim-less
RUN git clone --recursive https://github.com/tpope/vim-git $HOME/.vim/bundle/vim-git
RUN git clone --recursive https://github.com/tpope/vim-fugitive $HOME/.vim/bundle/vim-fugitive
RUN git clone --recursive https://github.com/scrooloose/syntastic $HOME/.vim/bundle/syntastic
RUN git clone --recursive https://github.com/Shougo/neosnippet $HOME/.vim/bundle/neosnippet
RUN git clone --recursive https://github.com/Valloric/YouCompleteMe $HOME/.vim/bundle/YouCompleteMe
RUN git clone --recursive https://github.com/dhazel/conque-term $HOME/.vim/bundle/conque-term
RUN git clone --recursive https://github.com/mattn/webapi-vim $HOME/.vim/bundle/webapi-vim
RUN git clone --recursive https://github.com/mattn/gist-vim $HOME/.vim/bundle/gist-vim
RUN git clone --recursive https://github.com/wavded/vim-stylus $HOME/.vim/bundle/vim-stylus
RUN git clone --recursive https://github.com/ciaranm/securemodelines $HOME/.vim/bundle/securemodelines
RUN git clone --recursive https://github.com/rizzatti/funcoo.vim $HOME/.vim/bundle/funcoo.vim
RUN git clone --recursive https://github.com/rizzatti/dash.vim $HOME/.vim/bundle/dash.vim
RUN git clone --recursive https://github.com/dag/vim-fish $HOME/.vim/bundle/vim-fish
RUN git clone --recursive https://github.com/godlygeek/tabular $HOME/.vim/bundle/tabular
RUN git clone --recursive https://github.com/nathanaelkane/vim-indent-guides $HOME/.vim/bundle/vim-indent-guides
RUN git clone --recursive https://github.com/dart-lang/dart-vim-plugin $HOME/.vim/bundle/dart-vim-plugin
RUN git clone --recursive https://github.com/kchmck/vim-coffee-script $HOME/.vim/bundle/vim-coffee-script
RUN git clone --recursive https://github.com/rking/ag.vim $HOME/.vim/bundle/ag.vim
RUN git clone --recursive https://github.com/klen/python-mode $HOME/.vim/bundle/python-mode
RUN git clone --recursive https://github.com/davidhalter/jedi-vim $HOME/.vim/bundle/jedi-vim
RUN git clone --recursive https://github.com/bling/vim-airline $HOME/.vim/bundle/vim-airline
RUN git clone --recursive https://github.com/tebriel/logstash.vim $HOME/.vim/bundle/logstash.vim
RUN git clone --recursive https://github.com/tpope/vim-rails $HOME/.vim/bundle/vim-rails
RUN git clone --recursive https://github.com/KurtPreston/vim-autoformat-rails $HOME/.vim/bundle/vim-autoformat-rails
RUN git clone --recursive https://github.com/derekwyatt/vim-scala $HOME/.vim/bundle/vim-scala

WORKDIR $HOME/.vim/bundle/YouCompleteMe

RUN ./install.py --clang-completer

RUN mkdir $HOME/workdir

WORKDIR $HOME/workdir

CMD ["vim"]
