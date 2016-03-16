##Vundle安装
> git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle

###Vundle简介
bundle分为三类：

    在Github vim-scripts 用户下的repos,只需要写出repos名称
    在Github其他用户下的repos, 需要写出”用户名/repos名”
    不在Github上的插件，需要写出git全路径

安装插件：

    打开一个vim, 运行:BundleInstall
    或者在命令行运行 vim +BundleInstall +qall
    安装完成后插件就能用了

其它常用命令：

    更新插件:BundleUpdate
    清除不再使用的插件:BundleClean,
    列出所有插件:BundleList
    查找插件:BundleSearch

####有用链接：
[vim中的杀手级插件：vundle](http://zuyunfei.com/2013/04/12/killer-plugin-of-vim-vundle/)

[使用vundle进行插件管理](http://www.jianshu.com/p/mHUR4e)

[Ctrlp](http://zuyunfei.com/2013/08/26/vim-plugin-ctrlp/)

[Vim插件Ctrlp](http://www.wklken.me/posts/2015/06/07/vim-plugin-syntastic.html)

[Syntax](http://www.wklken.me/posts/2015/06/07/vim-plugin-syntastic.html)

####编辑一下内容到~/.vimrc：
```
set nocompatible                " be iMproved
filetype off                    " required!
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()

" let Vundle manage Vundle
Bundle 'gmarik/vundle'

"my Bundle here:
"
" original repos on github
Bundle 'kien/ctrlp.vim'
" Bundle 'sukima/xmledit'
" Bundle 'sjl/gundo.vim'
" Bundle 'jiangmiao/auto-pairs'
" Bundle 'klen/python-mode'
" Bundle 'Valloric/ListToggle'
" Bundle 'SirVer/ultisnips'
Bundle 'Valloric/YouCompleteMe'
Bundle 'scrooloose/syntastic'
" Bundle 't9md/vim-quickhl'
" Bundle 'Lokaltog/vim-powerline'
Bundle 'scrooloose/nerdcommenter'
Bundle 'scrooloose/nerdtree'
"..................................
" vim-scripts repos
" Bundle 'YankRing.vim'
" Bundle 'vcscommand.vim'
" Bundle 'ShowPairs'
" Bundle 'SudoEdit.vim'
" Bundle 'EasyGrep'
" Bundle 'VOoM'
" Bundle 'VimIM'
"..................................
" non github repos
" Bundle 'git://git.wincent.com/command-t.git'
"......................................
filetype plugin indent on

let g:NERDTreeDirArrows=0
map <F1> :NERDTreeToggle<CR>
set nu!
```
