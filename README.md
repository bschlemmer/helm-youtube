[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/hyperium/hyper/master/LICENSE)

#Helm-YouTube
<p align="center">
  <img src="https://github.com/maximus12793/helm-youtube/blob/master/demo.gif">
</p>

Helm-YouTube is a simple plugin to query YouTube via emacs and play videos in your browser. 

**IMPORTANT:** Remeber to set your 'helm-youtube-key' variable!

## Installation 
1. M-x package-install: helm-youtube

2. Obtain new google API key 
    [here](https://console.developers.google.com/ "Google Developer Console")

    ![Screenshot](https://github.com/maximus12793/helm-youtube/blob/master/api.png)

3. Enable "Youtube Data API" for that key.

   3a. click "Youtube Data API"
   
   3b. click "ENABLE" on the next screen.
   
    ![screenshot2](https://github.com/academikuser/helm-youtube/blob/master/youtube-api.png)

4. **IMPORTANT:** Set 'helm-youtube-key' variable


    ``` el
    M-x customize-variable ;; search 'helm-youtube-key'
    Helm Youtube Key: replace "NONE" with "API KEY" ;; FROM STEP 2
    ```

5. Set browse-url-generic and add to .emacs

 
    ``` el
    ;;start helm-youtube.el
    (autoload 'helm-youtube "helm-youtube" nil t)
    (global-set-key (kbd "C-c y") 'helm-youtube) ;; bind hotkey

    ;;set default browser for you will use to play videos/default generic
    (setq browse-url-browser-function 'browse-url-generic)
    (setq browse-url-generic-program "google-chrome-open-url")
    ```
    
 5b. (alternative) osX - open with default browser for the os.
 
    ```el
      (setq browse-url-browser-function 'browse-url-generic
        browse-url-generic-program "open")            
    ```
 
6. Enjoy :) 
