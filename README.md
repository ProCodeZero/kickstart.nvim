### Languages Supported

| Language          | Tooling                                  | Purpose                   |
| ----------------- | ---------------------------------------- | ------------------------- |
| **Go** 🐹         | `gopls`, `neotest-golang`, `nvim-dap-go` | Primary backend language  |
| **Rust** 🦀       | `rust_analyzer`                          | Systems programming       |
| **Lua**           | `lua_ls`, `stylua`                       | Neovim config + scripting |
| **TypeScript/JS** | `vtsls`, `prettier`                      | Frontend/Full-stack       |
| **Zig**           | `zls`                                    | Emerging systems language |
| **PHP**           | `php.nvim`                               | Legacy/web projects       |
| **Templ**         | tree-sitter parser                       | Go HTML templating        |

---

## ⌨️ Core Workflow Patterns

### 🔍 Navigation & Search

```lua
<leader>pf   -- Fuzzy find files (Telescope)
<C-p>        -- Git-tracked files only
<leader>ps   -- Grep search with prompt
<leader>pws  -- Grep word under cursor
<C-e>        -- Harpoon quick menu (project marks)
<leader>a    -- Add file to Harpoon list
<M-1>..4     -- Jump to Harpoon mark 1-4
```

→ **Philosophy**: Minimize file switching friction; keep frequently-used files instantly accessible.

### 🛠️ LSP-Powered Editing

```lua
gd           -- Go to definition
K            -- Hover documentation
<leader>vca  -- Code actions (fixes, refactors)
<leader>vrn  -- Rename symbol
<leader>vd   -- Show diagnostics float
[d / ]d      -- Jump to next/prev diagnostic
```

→ **Philosophy**: Never leave the keyboard for IDE-like intelligence.

### 🐞 Debugging & Testing

```lua
-- Debugging (DAP)
<F8>         -- Continue
<F10>-<F12>  -- Step over/into/out
<leader>b    -- Toggle breakpoint
<leader>dr/ds/dw -- Toggle debug UI panels

-- Testing (Neotest)
<leader>tr   -- Run nearest test
<leader>ts   -- Run test suite
<leader>td   -- Debug nearest test
<leader>tv   -- Toggle test summary
```

→ **Philosophy**: Tight feedback loop for TDD; debug without leaving Neovim.

### 🌿 Git Integration

```lua
<leader>gs   -- Open Git status (Fugitive)
<leader>p    -- Push (in fugitive buffer)
<leader>P    -- Pull --rebase
<leader>t    -- Setup upstream branch
gu / gh      -- Accept merge conflict changes
```

→ **Philosophy**: Git is a first-class citizen; resolve conflicts with vim motions.

### 🎨 UX & Ergonomics

```lua
jk → <Esc>   -- Fast escape from insert mode
<C-d>/<C-u>  -- Scroll with cursor centered
n/N          -- Search with view centered
<leader>y/d  -- System clipboard integration
<leader>f    -- Format buffer (conform.nvim)
<leader>zz   -- Zen mode (distraction-free)
```

→ **Philosophy**: Reduce hand travel, keep context, stay in flow.

---

## 🧩 Tooling Philosophy

| Principle                  | Implementation                                                         |
| -------------------------- | ---------------------------------------------------------------------- |
| **Speed**                  | Telescope + Harpoon for instant navigation; lazy.nvim for fast startup |
| **Keyboard-first**         | Every action has a `<leader>` or motion-based binding                  |
| **Language-server driven** | LSP for completions, diagnostics, refactors across all languages       |
| **Test/Debug integrated**  | Neotest + DAP = full dev loop inside Neovim                            |
| **Terminal-aware**         | tmux-sessionizer bindings; DAP UI auto-closes tmux windows             |
| **Minimal but powerful**   | No heavy GUI; colorschemes toggle by filetype for visual context       |
| **Secure by default**      | `cloak.nvim` hides secrets in `.env` files                             |
