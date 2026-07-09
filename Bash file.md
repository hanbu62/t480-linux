```bash
source ~/.local/share/omakub/defaults/bash/rc

# Editor used by CLI
export EDITOR="nvim"
export SUDO_EDITOR="$EDITOR"
. "$HOME/.cargo/env"

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

alias stayawake='systemd-inhibit --what=idle --who="Manual" --why="Staying awake"'
alias killawake='pkill -f "systemd-inhibit.*sleep"'

alias jellyfin='flatpak run org.jellyfin.JellyfinServer'
alias jellyfin-restart='flatpak kill org.jellyfin.JellyfinServer && flatpak run org.jellyfin.JellyfinServer &'

```