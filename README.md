### tmuxinator
---

https://github.com/tmuxinator/tmuxinator

```
gem install tmuxinator
echo $EDITOR
export EDITOR='vim'

~/.bashrb
source ~/.bin/tmuxinator.bash

~/.zshrc
source ~/.bin/tmuxinator.zsh

cp ~/.bin/tmuxinator.fish ~/.config/fish/completions/

tmuxinator new [project]

tmuxinator start project workspace=~/workspace/todo

tmuxinator start [project] -n [name] -p [project-config]

mux [command]

tmuxinator copy [existing] [new]

tmuxinator list
tmuxinator delete [project]
tmuxinator implode
tmuxinator doctor
tmuxinator help
tmuxinator debug [project]
tmuxinator version

```

```ruby
```

```
# ~/.tmuxinator/sample.yml
name: sample
root: ~/

windows:
  - editor: main-vertical
      layout: main-vertial
      panes:
        - vim
        - guard
  - server: bundle exec rails s
  - logs: tail -f log/development.log
  
windows:
  - editor: vim

name: test
root: ~/projects/company

windows:
  - small_project:
      root: ~/projects/company/small_prject
      penes:
        - start this
        - start that
        
windows:
  - editor:
      layout: main-vertical
      penes:
        - vim
        - guard
        
pre_window: rbenv shell 2.0.0-p247

attach: false

on_project_start: tmux -C attach

name: sample
root: ~/
windows:
  - stats:
    - ssh stats@example.com
    - tail -f /var/log/stats.log
  - logs:
      layout: main-vertical
      penes:
        - logs:
          - ssh logs@example.com
          - cd /var/logs
          - tail -f development.log
          
root: <%= ENV["MY_CUSTOM_DIR"] %>
  
~/.tmuxinator/project.yml
name: project
root: ~/<%= @args[0] %>

name: project
root: ~/<%= @settings["workspace"]%>
```

