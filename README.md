# tmuxkSetting for emacs usuer
ref:https://nantonaku-shiawase.hatenablog.com/entry/2021/02/04/231415



# tmux in vscode
tmuxをvscodeで使うと文字がコピーができない現象に遭遇．ここで議論されてるけど根本的な解決策はなかった(https://github.com/microsoft/vscode/issues/209191)
しばらくはhistoryをemacs で開いてコピーで対応
bashrcに以下を記載のこと．
```bash
export HISTSIZE=10000
export HISTFILESIZE=10000
#export HISTIGNORE=ls:history:pwd
#export HISTTIMEFORMAT='%Y/%m/%d %H:%M:%S, '
function share_history {
    history -a
    history -n
}
PROMPT_COMMAND='share_history'
shopt -s histappend
```
