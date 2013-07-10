### cmuclojure.el --- Clojure process in a buffer

Copyright (C) 2013  Jude Chao  
Author: Jude Chao  
Email: <kaihaosw@gmail.com>  
Version: 0.1  

Based on cmuscheme.el and https://github.com/syohex/emacs-inf-clojure/blob/master/inf-clojure.el  

I just need run clojure in a buffer, and send the function to the buffer immediately.  
So there are just a few methods. But it's enough for me now.  
Some more methods will come as soom as needed.  

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

This program is free software; you can redistribute it and/or modify  
it under the terms of the GNU General Public License as published by  
the Free Software Foundation, either version 3 of the License, or  
(at your option) any later version.  

This program is distributed in the hope that it will be useful,  
but WITHOUT ANY WARRANTY; without even the implied warranty of  
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the  
GNU General Public License for more details.  

You should have received a copy of the GNU General Public License  
along with this program.  If not, see <http://www.gnu.org/licenses/>.  
