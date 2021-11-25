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
"This is for showing buffers only
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#show_buffers = 0
let g:airline#extensions#tabline#show_splits = 0
let g:airline#extensions#tabline#show_tabs = 1
let g:airline#extensions#tabline#show_tab_nr = 0
let g:airline#extensions#tabline#show_tab_type = 0
let g:airline#extensions#tabline#close_symbol = '×'
let g:airline#extensions#tabline#show_close_button = 0
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
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
map <C-h> <C-w>h
map <C-Left> <C-w>h
map <C-j> <C-w>j
map <C-Down> <C-w>j
map <C-Up> <C-w>k
map <C-k> <C-w>k
map <C-Right> <C-w>l
map <C-l> <C-w>l
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

### For Terminal toggling
```typescipt
" Terminal Function
let g:term_buf = 0
let g:term_win = 0
function! TermToggle(height)
    if win_gotoid(g:term_win)
        hide
    else
        botright new
        exec "resize " . a:height
        try
            exec "buffer " . g:term_buf
        catch
            call termopen($SHELL, {"detach": 0})
            let g:term_buf = bufnr("")
            set nonumber
            set norelativenumber
            set signcolumn=no
        endtry
        startinsert!
        let g:term_win = win_getid()
    endif
endfunction
```
```typescript
" Toggle terminal on/off (neovim)
nnoremap <A-t> :call TermToggle(12)<CR>
inoremap <A-t> <Esc>:call TermToggle(12)<CR>
tnoremap <A-t> <C-\><C-n>:call TermToggle(12)<CR>

" Terminal go back to normal mode
tnoremap <Esc> <C-\><C-n>
tnoremap :q! <C-\><C-n>:q!<CR>
```
