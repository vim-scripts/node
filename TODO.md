" Save existing includeexpr to later fall back on it.
let includeexpr = escape(&includeexpr, "'")
exe "setl includeexpr=" . s:snr() . "find(v:fname,'" . includeexpr . "')"

" TODO: Fall back to previous includeexpr, but make sure to not eval
" it when it came from the modeline. Even though modeline overwrites the
" includeexpr set by this plugin, better be safe than sorry.
function! s:find(name, fallback)
