  To get only directories with  fzf , use the  --walker  option:

    fzf --walker dir

  Or if you want to combine it with other walker options:

    fzf --walker dir,follow,hidden

  The  --walker  option controls which types of items the built-in directory
  walker includes:

  •  file  - Include files
  •  dir  - Include directories only
  •  follow  - Follow symbolic links
  •  hidden  - Include and follow hidden directories

  So  --walker dir  gives you directories only, while  --walker dir,follow,
  hidden
  includes directories (and hidden ones), following symlinks.