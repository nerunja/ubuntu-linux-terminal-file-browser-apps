# Terminal File Browsers for Ubuntu

A comprehensive guide to terminal-based file managers available for Ubuntu Desktop and Server.

---

## Quick Comparison Table

| Name | Layout Style | Language | Keybindings | Best For | Installation | Size/Speed |
|------|-------------|----------|-------------|----------|--------------|------------|
| **mc** | Dual-pane | C | F-keys, Mouse | Traditional users, VFS needs | `apt install mc` | Medium/Fast |
| **vifm** | Dual-pane | C | Vi/Vim | Vim users, modal editing | `apt install vifm` | Small/Fast |
| **ranger** | 3-column Miller | Python | Vi-style | Rich previews, Python scripting | `apt install ranger` | Medium/Medium |
| **nnn** | Single/Multi-context | C | Custom | Speed, plugins, minimal deps | `apt install nnn` | Tiny/Very Fast |
| **lf** | 3-column Miller | Go | Vi-style | Speed, single binary | Manual/GitHub | Small/Very Fast |
| **fff** | Single pane | Bash | Simple | Learning, customization | Manual/GitHub | Tiny/Fast |
| **broot** | Tree + search | Rust | Fuzzy search | Large dirs, pattern navigation | `apt install broot` | Small/Fast |
| **clifm** | Shell-like | C | Shell-style | CLI users, bookmarks | Manual/snap | Small/Fast |
| **joshuto** | 3-column Miller | Rust | Vi-style | Modern Rust alternative | Manual/cargo | Small/Very Fast |
| **xplr** | Customizable | Rust | Mode-based | Lua config, hackability | Manual/cargo | Small/Fast |

---

## Detailed Breakdown

### Traditional Two-Panel Managers

#### mc (Midnight Commander)
**What's Good:**
- Classic Norton Commander-style interface with dual panels
- Built-in editor (mcedit), viewer, and diff tool
- VFS (Virtual File System) support for archives, FTP, SFTP, cloud storage
- Highly stable, battle-tested for decades
- Full mouse support in terminal
- Function key shortcuts (F3-view, F4-edit, F5-copy, F6-move, F8-delete)
- Available in all distro repositories
- Great for users from DOS/Windows Commander era

**Installation:**
```bash
sudo apt install mc
```

**Usage:**
```bash
mc
```

---

#### vifm
**What's Good:**
- Vi/Vim-style keybindings throughout (h/j/k/l navigation)
- Dual-pane layout with modal editing approach
- Highly customizable with vifmrc configuration
- Preview pane support
- Can use external tools for previews (bat, highlight, etc.)
- Fast and lightweight
- Perfect for Vim users - feels completely natural
- Tabs support for multiple directory pairs

**Installation:**
```bash
sudo apt install vifm
```

**Usage:**
```bash
vifm
```

---

### Modern Minimalist Managers

#### ranger
**What's Good:**
- Three-column Miller view (parent/current/preview)
- Vi keybindings with extensive customization
- Rich file previews: images (w3m-img), videos (ffmpeg), documents, code
- Syntax highlighting in previews
- Bulk renaming capability with built-in tool
- Highly scriptable and extensible with Python
- Rifle file opener with intelligent defaults
- Bookmarks and tab support
- Can integrate with image viewers like ueberzug for better image preview

**Installation:**
```bash
sudo apt install ranger
```

**Enhanced with previews:**
```bash
sudo apt install ranger w3m-img highlight atool mediainfo
```

**Usage:**
```bash
ranger
```

---

#### nnn
**What's Good:**
- Extremely fast and lightweight (~100KB binary, minimal RAM)
- Minimal dependencies - runs almost anywhere
- Plugin architecture (60+ plugins available)
- Disk usage analyzer built-in (du mode)
- Batch operations support with selection
- Desktop integration - open files in GUI apps
- Multiple contexts (can spawn 4 independent sessions)
- Live reload of directory changes
- Typeahead search
- One of the fastest file managers available

**Installation:**
```bash
sudo apt install nnn
```

**Usage:**
```bash
nnn
# Or with context support
nnn -c
```

**Plugins:**
```bash
# Enable plugins
export NNN_PLUG='p:preview-tui;d:diffs;m:nmount'
```

---

#### lf (list files)
**What's Good:**
- Inspired by ranger but written in Go (single static binary)
- Very fast startup and operation
- Asynchronous operations don't block UI
- Customizable with shell commands in config
- Remote file editing support
- Three-pane layout similar to ranger
- Server/client architecture for remote control
- Cross-platform (Linux, macOS, Windows)

**Installation:**
```bash
# Download from GitHub releases
wget https://github.com/gokcehan/lf/releases/download/r31/lf-linux-amd64.tar.gz
tar -xzf lf-linux-amd64.tar.gz
sudo mv lf /usr/local/bin/
```

**Usage:**
```bash
lf
```

---

#### fff (Fast File Manager)
**What's Good:**
- Pure Bash script (~800 lines)
- Extremely simple and hackable
- Very fast startup
- Image previews with w3m-img
- Easy to understand and modify the source
- No dependencies beyond bash
- Great for learning shell scripting
- Lightweight enough for embedded systems

**Installation:**
```bash
# Install from GitHub
git clone https://github.com/dylanaraps/fff
cd fff
sudo make install
```

**Usage:**
```bash
fff
```

---

### Next-Gen Interactive Tools

#### broot
**What's Good:**
- Tree view with fuzzy search built-in
- Fast directory navigation with pattern matching
- Preview pane for files
- Git integration showing file status and changes
- Can handle huge directories efficiently (millions of files)
- Modern command syntax with verbs
- Can launch external commands on selections
- "br" shell function for cd integration
- Size information and filtering by size

**Installation:**
```bash
sudo apt install broot
```

**Setup shell integration:**
```bash
broot --install
```

**Usage:**
```bash
broot
# Or use br to cd to selected directory
br
```

---

#### clifm
**What's Good:**
- Shell-like interface with tab autocomplete
- Bookmark system for quick navigation
- Trash support (move to trash instead of delete)
- Fast search with filters
- Traditional command-line feel with file manager benefits
- Can execute shell commands directly
- Color schemes and customizable prompts
- Resource opener for file associations
- Regex support in operations

**Installation:**
```bash
sudo snap install clifm
# Or from source/PPA
```

**Usage:**
```bash
clifm
```

---

#### joshuto
**What's Good:**
- Ranger-like interface but written in Rust
- Modern, clean codebase
- Three-column Miller layout
- Fast performance with low resource usage
- Configurable with TOML files
- Asynchronous I/O operations
- Tab support
- Trash support
- Active development with modern features

**Installation:**
```bash
# Via cargo
cargo install --git https://github.com/kamiyaa/joshuto.git --force
```

**Usage:**
```bash
joshuto
```

---

#### xplr
**What's Good:**
- Hackable and minimal by design
- Lua configuration for extensive customization
- Mode-based interaction (like Vim)
- Pipeline-friendly - integrates with other CLI tools
- Can pipe file lists to other commands
- Fast and lightweight
- Plugin system via Lua
- Column-based layout
- Built-in multiplexing

**Installation:**
```bash
# Download binary from releases
wget https://github.com/sayanarijit/xplr/releases/download/v0.21.7/xplr-linux.tar.gz
tar -xzf xplr-linux.tar.gz
sudo mv xplr /usr/local/bin/
```

**Usage:**
```bash
xplr
```

---

## Feature Matrix

| Feature | mc | vifm | ranger | nnn | lf | broot |
|---------|----|----|--------|-----|-----|-------|
| **Dual Pane** | ✅ | ✅ | ✅ (3-col) | ✅ (contexts) | ✅ (3-col) | ❌ |
| **Image Preview** | ❌ | ⚠️ (external) | ✅ | ⚠️ (plugin) | ⚠️ (config) | ⚠️ (limited) |
| **Archive Support** | ✅ (VFS) | ⚠️ (limited) | ✅ | ⚠️ (plugin) | ⚠️ (config) | ❌ |
| **FTP/SFTP** | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ |
| **Built-in Editor** | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Tabs** | ❌ | ✅ | ✅ | ✅ (contexts) | ✅ | ❌ |
| **Bookmarks** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| **Bulk Rename** | ✅ | ✅ | ✅ | ⚠️ (plugin) | ⚠️ (config) | ❌ |
| **Trash Support** | ❌ | ✅ | ❌ | ⚠️ (plugin) | ⚠️ (config) | ❌ |
| **Git Integration** | ❌ | ⚠️ (limited) | ❌ | ⚠️ (plugin) | ❌ | ✅ |
| **Fuzzy Search** | ❌ | ❌ | ⚠️ (plugin) | ✅ | ❌ | ✅ |
| **Mouse Support** | ✅ | ⚠️ (limited) | ⚠️ (limited) | ❌ | ❌ | ✅ |

Legend: ✅ Native | ⚠️ Via plugins/config | ❌ Not available

---

## Quick Decision Guide

### Choose **mc** if you:
- Want something immediately available and reliable
- Like Norton Commander or Total Commander
- Need VFS features (archives, FTP, SFTP as directories)
- Prefer function keys over keyboard shortcuts
- Want a built-in text editor

### Choose **vifm** if you:
- Are a Vim user and want familiar keybindings
- Like modal editing everywhere
- Need dual-pane with Vim workflow
- Want extensive customization with vifmrc

### Choose **ranger** if you:
- Want rich file previews (images, videos, documents)
- Like three-column Miller view
- Need Python scriptability
- Want Vi keybindings with good defaults

### Choose **nnn** if you:
- Want the fastest, lightest option
- Need minimal dependencies (works on minimal systems)
- Like plugin architecture
- Want multiple independent contexts
- Need to work on remote/embedded systems

### Choose **lf** if you:
- Want ranger-like features with better performance
- Prefer a single binary with no dependencies
- Like Go-based tools
- Need asynchronous operations

### Choose **broot** if you:
- Work with large directory trees
- Want fuzzy search as primary navigation
- Need Git integration
- Like modern command syntax
- Often navigate deep directory structures

---

## Installation Quick Reference

```bash
# From Ubuntu repositories
sudo apt install mc vifm ranger nnn broot

# Optional dependencies for better experience
sudo apt install w3m-img highlight atool mediainfo poppler-utils

# For Rust-based tools (if not in repos)
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo install joshuto xplr

# For Go-based tools
# Download from respective GitHub releases pages
```

---

## Common Keybindings Comparison

| Action | mc | vifm | ranger | nnn |
|--------|-----|------|--------|-----|
| **Navigate** | Arrows | hjkl | hjkl | hjkl |
| **Go up dir** | Arrows | h | h | h or - |
| **Enter dir** | Enter | l | l | Enter or l |
| **View file** | F3 | i | i | p (plugin) |
| **Edit file** | F4 | e | E | e |
| **Copy** | F5 | yy | yy | Ctrl+k |
| **Move** | F6 | dd | dd | Ctrl+v |
| **Delete** | F8 | dd | dD | Ctrl+x |
| **Search** | Alt+? | / | / | / |
| **Shell** | Ctrl+o | :! | S | ! |
| **Quit** | F10 | q or ZZ | q or ZZ | q |

---

## Performance Characteristics

Based on typical usage patterns:

**Startup Speed (fast to slow):**
1. nnn (~instant)
2. lf (~instant)
3. fff (~instant)
4. joshuto (very fast)
5. vifm (fast)
6. mc (fast)
7. broot (fast, but indexes)
8. ranger (slower, Python startup)

**Memory Usage (low to high):**
1. fff (~5 MB)
2. nnn (~10 MB)
3. lf (~15 MB)
4. vifm (~20 MB)
5. mc (~25 MB)
6. joshuto (~30 MB)
7. broot (~40 MB)
8. ranger (~50-80 MB with previews)

**Large Directory Performance (best to worst):**
1. nnn
2. lf
3. broot (with indexing)
4. joshuto
5. vifm
6. mc
7. ranger

---

## Additional Resources

- **mc**: https://midnight-commander.org/
- **vifm**: https://vifm.info/
- **ranger**: https://github.com/ranger/ranger
- **nnn**: https://github.com/jarun/nnn
- **lf**: https://github.com/gokcehan/lf
- **fff**: https://github.com/dylanaraps/fff
- **broot**: https://github.com/Cantido/broot
- **clifm**: https://github.com/leo-arch/clifm
- **joshuto**: https://github.com/kamiyaa/joshuto
- **xplr**: https://github.com/sayanarijit/xplr

---

## Tips for Getting Started

1. **Start with what's in the repos**: mc, vifm, ranger, and nnn are readily available via apt
2. **Try before you customize**: Use defaults first to understand the tool
3. **Check the help**: Most use `?` or `h` to show keybindings
4. **Install preview dependencies**: w3m-img, highlight, and mediainfo greatly improve experience
5. **Configure your shell**: Some tools (like broot) work better with shell integration
6. **Learn one well**: Don't tool-hop too much; master one that fits your workflow

---

*Last updated: November 2025*
*Ubuntu versions: 22.04 LTS, 24.04 LTS, 25.04*
