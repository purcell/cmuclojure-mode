### cmuclojure.el --- Clojure process in a buffer

License: GPL
Copyright (C) 2013  Jude Chao  
Author: Jude Chao  
Email: <kaihaosw@gmail.com>  
Version: 0.1  

Based on cmuscheme.el and https://github.com/syohex/emacs-inf-clojure/blob/master/inf-clojure.el  

I just need run clojure in a buffer, and send the function to the buffer immediately.  
So there are just a few of methods. But it's enough for me now.  
More methods will come as soon as needed.  

### Install
It's available at marmalade.

    (require 'cmuclojure)

### Avaliable method: (M-x)

    clojure-send-region
    clojure-send-definition
    clojure-send-definition-split-window

### Trick

    (add-hook 'cmuclojure-load-hook
        (lambda ()
            (define-key clojure-mode-map (kbd "C-c C-c") 'clojure-send-definition-split-window)
            ;; ...
            (paredit-mode 1)
            (add-hook 'cmuclojure-load-hook (paren-face-add-support clojure-font-lock-keywords))))
