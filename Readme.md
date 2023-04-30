<div>
  <div>
    <div><div style="background-color: rgb(16, 163, 127)"></div></div>
    <div>
      <div>
        <div>
          <div>
            <h1>Setup Guide for making your boring Terminal Interesting!</h1>
                       <img src="./screenshot.png" alt="screenshot"/>
            <p>
Ah, so you want to add some magic to your command line? Well, you've come to the right place my friend!
            </p>
            <h2>Prerequisites</h2>
            <p>
              Before getting started, make sure you have the following tools
              installed:
            </p>
            <ul>
              <li>Kitty terminal emulator</li>
              <li>Tmux terminal multiplexer</li>
            </ul>
            <p>
              Use the following commands to install the prerequisites based on
              your Linux distribution:
            </p>
            <ul>
              <li>Fedora: <code>sudo dnf install kitty tmux i3</code></li>
              <li>
                Debian/Ubuntu: <code>sudo apt-get install kitty tmux i3</code>
              </li>
            </ul>
            <h2>Kitty Setup</h2>
            <p>
              Once you have Kitty installed, open it and use the following
              command to install the <code>kitten themes</code> plugin:
            </p>
            <pre><div ><div ></div><div ><code >kitty +kitten themes
</code></div></div></pre>
             <p>
              Now let's make kitty transparent:
            </p>
            <pre><div ><div ></div><div ><code>gedit ~/.config/kitty/current-theme.conf
</code></div></div></pre>
            <p>add <code>background_opacity 0.8</code></p>
            <p>
              Now, let's change the default font to a more visually appealing
              font. Install the * Hack Nerd * Font by following the instructions on
              their website:
              <a href="https://www.nerdfonts.com/font-downloads" target="_new"
                >https://www.nerdfonts.com/font-downloads</a
              >
            </p>
            <p>
              Press <code>ctrl+shift+f2</code> inside Kitty and paste the
              following configuration:
            </p>
            <pre><div ><div ><span># font_family      Input Mono </span></div><div ><code >font_family     Hack Nerd <span >Font</span> Regular
italic_font     Hack Nerd <span >Font</span> Italic
bold_font       Hack Nerd <span >Font</span> Bold
bold_italic_font Hack Nerd <span >Font</span> Bold Italic
</code></div></div></pre>
            <h2>OhMyZsh Setup</h2>
            <p>
              Zsh is a popular shell that offers more features and customization
              than the default Bash shell. Install OhMyZsh ~a plugin manager for zsh shell by using the following
              command:
            </p>
            <pre><div ><div ><span></span></div><div ><code >sh -c <span >"<span >$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)</span>"</span>
</code></div></div></pre>
            <p>
            But first make sure zsh & fzf is installed <code>sudo dnf install zsh</code> then after the first configuration --> <code>git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf ~/.fzf/install</code>
            </p>
            <p>Now make zsh your primary shell:</p>
<pre><div ><div ></div><div ><code >chsh -s $(which zsh)
</code></div></div></pre>
<p>if chsh not installed it will prompt you to install it! press y</p>
            <p>
              Next, install the <code>colorls</code> gem, which adds color and
              icons to the <code>ls</code> command:
            </p>
            <p>For debian:</p>
                        <pre><div ><div ></div><div ><code >sudo apt-get install ruby ruby-dev
</code></div></div></pre>
<p>For fedora:</p>
<pre><div ><div ></div><div ><code >sudo dnf install ruby
</code></div></div></pre>
<pre><div ><div ></div><div ><code >sudo dnf install ruby-devel
</code></div></div></pre>
<pre><div ><div ></div><div ><code >sudo dnf install gem
</code></div></div></pre>
<p>Now make sure gcc and g++ is installed then install the gem</p>
            <pre><div ><div ></div><div ><code >gem install colorls
</code></div></div></pre>
            <p>
              Now, let's add some magic to your shell by installing the popular
              <code>powerlevel10k</code> theme,
              <code>zsh-syntax-highlighting</code> plugin, and
              <code>zsh-autosuggestions</code> plugin:
            </p>
            <pre><div ><div ></div><div ><code >git <span >clone</span> --depth=1 https://github.com/romkatv/powerlevel10k.git <span >${ZSH_CUSTOM:-<span >$HOME</span>/.oh-my-zsh/custom}</span>/themes/powerlevel10k
git <span >clone</span> https://github.com/zsh-users/zsh-syntax-highlighting.git <span >${ZSH_CUSTOM:-~/.oh-my-zsh/custom}</span>/plugins/zsh-syntax-highlighting
git <span >clone</span> https://github.com/zsh-users/zsh-autosuggestions <span >${ZSH_CUSTOM:-~/.oh-my-zsh/custom}</span>/plugins/zsh-autosuggestions
</code></div></div></pre>
            <p>
              Next, copy the <code>.zshrc</code> file from this repository
              to your home directory:
            </p>
            <pre><div ><div ></div><div ><code ><span >cp</span> .zshrc ~/.zshrc
</code></div></div></pre>
            <p>
              Now edit the .zshrc and replace all occurances of `coffee-plz` in the file with your unix username (the one that shows up in your terminal)
            </p>
<p>Now source it and follow the power10k's prompted steps accordingly</p>
<pre><div ><div ></div><div ><code >source .zshrc 
</code></div></div></pre>
            <h2>TPM Setup</h2>
            <p>
              Tmux is a terminal multiplexer that allows you to split your
              terminal into multiple panes and windows. Install the tpm ~tmux plugin manager by using
              the following command:
            </p>
            <pre><div ><div></div><div ><code >git <span >clone</span> https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
</code></div></div></pre>
            <p>
              Next, copy the <code>.tmux.conf</code> file from this repository
              to your home directory:
            </p>
            <pre><div ><div ></div><div ><code ><span >cp</span> .tmux.conf ~/.tmux.conf
</code></div></div></pre>
            <p>
             Finally, start Tmux by entering the <code>tmux</code> command, and source your config file
            </p>
            <pre><div ><div ></div><div ><code > tmux source-file ~/.tmux.conf
</code></div></div></pre>
            <p>
              then press <code>ctrl-f I</code> to install the plugins using the
              Tmux Plugin Manager, and press <code>ctrl-f r</code> to reload the
              Tmux configuration.
            </p>
            <h2>🫰</h2>
            <p>
And voila! Your command line is now looking stylish, colorful, and powerful. You're now ready to take on the world, one command at a time!
            </p>
          </div>
        </div>
      </div>
  </div>
</div>

`go through the tmux config file and .zshrc file in this repo for all the keybinding and shortcuts`
