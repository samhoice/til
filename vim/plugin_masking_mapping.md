# Fix a plugin mapping masking another mapping

I installed a plugin that is masking a mapping with it's own mapping. There are two easy solutions here. First is to remap that mapping:

`nmap <localleader>- <Plug>VimwikiRemoveHeaderLevel`

The other is to unmap it:

`nunmap -`

I used the first, so I haven't tried the second.
