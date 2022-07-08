from https://zenn.dev/dwatarub/articles/saikyo-no-terminal
from https://qiita.com/navitime_tech/items/c249269a3b47666c784b

```
sudo apt install zsh

which zsh | sudo tee -a /etc/shells
chsh -s `which zsh`

git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"

setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done

prompt -s powerlevel10k

sudo apt install exa
sudo apt install bat

## zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
mv zsh-syntax-highlighting .zsh-syntax-highlighting

echo "source ${(q-)PWD}/.zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
source ./.zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

sudo apt install fd-find

curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
cargo install procs

sudo apt-get install ripgrep

nano .zshrc
+ alias ll="exa -l -h -@ -mU --icons --git --time-style=long-iso --color=automatic --group-directories-first"
+ alias l="ll -aa"
+ alias cat="batcat"
+ alias find="fdfind"
+ alias ps="procs"
+ alias grep="rg"

```
