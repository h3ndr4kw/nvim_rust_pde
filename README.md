# How to use

Install latest neovim


Backup exisiting Nvim configuration if any.
```
nv ~/.config/nvim ~/.config/nvim.bak
rm -fr ~/.local/share/nvim
```

Installed NvChad
```
git clone https://github.com/NvChad/NvChad ~/.config/nvim --depth 1 && nvim
```

Update Custom nvim configuration

remove NvChad initial custom configuration directory 
```
rm -fr ~/.config/nvim/lua/custom
```

clone cpp Custom configuration
```
git clone https://github.com/h3ndr4kw/nvim_rust_pde.git ~/.config/nvim/lua/custom
```

Add below in ~/.vimrc
```
nnoremap <A-j> :m .+1<CR>==
nnoremap <A-k> :m .-2<CR>==
inoremap <A-j> <Esc>:m .+1<CR>==gi
inoremap <A-k> <Esc>:m .-2<CR>==gi
vnoremap <A-j> :m '>+1<CR>gv=gv
vnoremap <A-k> :m '<-2<CR>gv=gv

```

Then open up neovim and let everything install.

```
:TSInstall rust
```

Install Latest Tmux
https://github.com/tmux/tmux

Install Tmux Plugin Manager

```
git clone https://github.com/tmux-plugins/tpm ~/.config/tmux/plugins/tpm
```

Create tmux configuration file in ~/.config/tmux/tmux.conf

```
set-option -sa terminal-overrides ",xterm*:Tc"
set -g mouse on

unbind C-b
set -g prefix C-Space
bind C-Space send-prefix

# Vim style pane selection
bind h select-pane -L
bind j select-pane -D 
bind k select-pane -U
bind l select-pane -R

# Start windows and panes at 1, not 0
set -g base-index 1
set -g pane-base-index 1
set-window-option -g pane-base-index 1
set-option -g renumber-windows on

# Use Alt-arrow keys without prefix key to switch panes
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# Shift arrow to switch windows
bind -n S-Left  previous-window
bind -n S-Right next-window

# Shift Alt vim keys to switch windows
bind -n M-H previous-window
bind -n M-L next-window

# Split panes with \ and -
bind \\ split-window -h -c "#{pane_current_path}"
bind - split-window -v -c "#{pane_current_path}"
unbind '"'
unbind % 

set -g @catppuccin_flavour 'mocha'

set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'christoomey/vim-tmux-navigator'
set -g @plugin 'dreamsofcode-io/catppuccin-tmux'
set -g @plugin 'tmux-plugins/tmux-yank'

run '~/.config/tmux/plugins/tpm/tpm'

# set vi-mode
set-window-option -g mode-keys vi
# keybindings
bind-key -T copy-mode-vi v send-keys -X begin-selection
bind-key -T copy-mode-vi C-v send-keys -X rectangle-toggle
bind-key -T copy-mode-vi y send-keys -X copy-selection-and-cancel

bind '"' split-window -v -c "#{pane_current_path}"
bind % split-window -h -c "#{pane_current_path}"
```

```
$ tmux
$ tmux source ~/.config/tmux/tmux.conf

```
install plugin prefix(CTRL+ladder) + I


Enjoy
