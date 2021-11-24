# vim-cheatsheet
## command
```
I  - Insert (Begin of the Line)
A  - Append (End of the Line)
o - New line below
O - New line above
w - Jump to next word
3w - Jump 3 words

b - Jump to previous Word
r - Replace letter
R - Replace mode
cw - Change word (the selected word is gone and enter insert mode)
c3w - Delete next 3 words and enter insert mode
3w - Jump 3 words
C - Delete Rest of Line and enter insert mode
dw - Delete word NOT enter insert mode
d4w - Delete four words NOT enter insert mode
D - Delete Rest of Line and NOT enter insert mode
4dd - Delete four lines
8cc - Change eight lines
ciw - Change inner word
ci ) or ci ( - Change inner parentheses
ci ] or ci [ - Change inner brackets
ci } or ci { - Change inner brackets
diw - Delete inner word

5u - Undo last 5 changes
7 CTRL+R - Redo 7 last things
% Jump to matched bracket
c% - Change until bracket
17G - 17th line
:17 - 17th line
$ - End of line
0 - Begin of the line
v - Visual Mode
p - Paste after
P -  Paste before
yi) - Yank in bracket
yiw - Yank inner word
V - Visual line
CTRL+V - Visual Block (column wise selection)
. - Repeat last operation
zz - center the screen
> - Shift right
< - Shift left
= - Indent
gg=G - Indent whole file
ggdG - Delete whole file

```
## vim-plug
https://github.com/junegunn/vim-plug
### Theme
https://github.com/morhetz/gruvbox
### Useful settings
```typescript=
set relativenumber
set nohlsearch
set tabstop=4 softtabstop=4
set hidden
set incsearch
set scrolloff=8
set noswapfile
set nobackup
set undodir=~/.vim/undodir
set undofile
set mouse=a
```
### Useful Plug
```typescript=
Plug 'nvim-lua/plenary.nvim'
Plug 'nvim-telescope/telescope.nvim'
Plug 'gruvbox-community/gruvbox'
Plug 'tomasiser/vim-code-dark'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'tpope/vim-fugitive'
Plug 'junegunn/fzf'
Plug 'junegunn/fzf.vim'
Plug 'preservim/nerdtree'
Plug 'tpope/vim-commentary' "For commenting
Plug 'ryanoasis/vim-devicons'
Plug 'tc50cal/vim-terminal'
Plug 'terryma/vim-multiple-cursors'
```

### Useful Map
```typescript=
nnoremap <silent> <expr> <C-\> g:NERDTree.IsOpen() ? "\:NERDTreeClose<CR>" : bufexists(expand('%')) ? "\:NERDTreeFind<CR>" : "\:N    ERDTree<CR>"
```
### For terminal color consistency
https://github.com/gruvbox-community/gruvbox
```
colorscheme gruvbox
set background=dark
highlight Normal ctermbg=none 
```
### For Telescope NVIM
https://github.com/neovim/neovim
https://github.com/BurntSushi/ripgrep
