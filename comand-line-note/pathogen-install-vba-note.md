#如何在pathogen中安装.vba?

##介绍vba
vim插件老式直接为.vim脚本,需要人工维护这样带给我们很多的麻烦!所以vim官方给出了.vba解决方案可是在原有的大量的.vim格式文件的存在下,给很多初学者带来了很多困难(我也是一个初学者哦),因此pathogen脱颖而出,给插件的安装和维护带来了很大的方便-小小易
##解决方案(官方版本)
 What about how to install Vimballs in pathogen?

If you really must use one:

    :e name.vba
    :!mkdir ~/.vim/bundle/name
    :UseVimball ~/.vim/bundle/name
That's all , so easy for that!
##解决方案(more easy to install)
<p
"--------------------------------------------------
" pathogen_install_vba.vim
" Author:       jiazhoulvke
" Email:        jiazhoulvke [AT] gmail.com
" Blog:         http://jiazhoulvke.com
" Version:      0.1
"--------------------------------------------------
 
if &cp || exists("g:loaded_pathogen_install_vba")
    finish
endif
let g:loaded_pathogen_install_vba="v0.1"
 
command! PathogenInstallVBA :call Pathogen_Install_VBA()
 
function! Pathogen_Install_VBA()
    let jzlk_extname=expand("%:e")
    if jzlk_extname!="vba"
        echo '这个文件不是vba安装包哦。'
    else
        let vba_dir_name=input("插件文件夹名: ")
        if has("win32")
            let vba_dir_path=$VIM . "\\vimfiles\\bundle\\" . vba_dir_name
            call system("md " . vba_dir_path)
        else
            let vba_dir_path="~/.vim/bundle/" . vba_dir_name
            call system("mkdir ". vba_dir_path)
        endif
        execute 'UseVimball ' . vba_dir_path
    endif
endfunction

