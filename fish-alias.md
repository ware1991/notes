~/.config/fish/config.fish

```
function fish_prompt ~/powerline-shell/powerline-shell.py $status --shell bare ^/dev/nullend

alias gg="cd ~/projects"alias ss="cd ~/erp-projects"alias inchlai="cd ~/weekendbooster/RichMan"

alias ..="cd .."alias ll="ls -al"alias sv="sudo vim"alias art="php artisan"alias migrate="php artisan migrate"alias rollback="php artisan migrate:rollback"alias phpunit="./vendor/bin/phpunit"

alias gs="git status"alias ga="git add ."alias gc="git commit -m"alias gp="git push origin"alias gl="git pull origin"alias gd="git diff"alias gb="git branch"alias gck="git checkout"
```