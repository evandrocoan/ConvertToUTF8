Description (中文说明见[README.zh_CN.md](https://github.com/seanliang/ConvertToUTF8/blob/master/README.zh_CN.md))
------------------
With this plugin, you can edit and save the files which encodings are not supported by Sublime Text currently, especially for those used by CJK users, such as GB2312, GBK, BIG5, EUC-KR, EUC-JP, etc. ConvertToUTF8 supports both Sublime Text 2 and 3.

![ConvertToUTF8](https://seanliang.github.io/donate/ConvertToUTF8.gif)

If you want to support this plugin, you can donate via Alipay or WeChat. Thanks! :)

![Alipay QR code](https://seanliang.github.io/donate/ap.png) ![WeChat QR code](https://seanliang.github.io/donate/wx.png)

Note
------------------
** Windows 7 (Sublime Text 3): When Windows DPI Scaling is set to a value higher than 100%, the file name might not be displayed correctly, please try to add `"dpi_scale": 1` to User Settings of Sublime Text.

** Linux (Sublime Text 2 & 3) and OSX (Sublime Text 3): You will need to install an extra plugin to make ConvertToUTF8 work properly: [Codecs26](https://github.com/seanliang/Codecs26) for Sublime Text 2 or [Codecs33](https://github.com/seanliang/Codecs33) for Sublime Text 3.


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
    wait few seconds until the installation finishes up
1. Now,
    Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    input the following address and press <kbd>Enter</kbd>
    ```
    https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
    ```
1. Go to the menu **`Tools -> Command Palette...
    (Ctrl+Shift+P)`**
1. Type **`Preferences:
    Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    find the following setting on your **`Package Control.sublime-settings`** file:
    ```js
    "channels":
    [
        "https://packagecontrol.io/channel_v3.json",
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
    ],
    ```
1. And,
    change it to the following, i.e.,
    put the **`https://raw.githubusercontent...`** line as first:
    ```js
    "channels":
    [
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
        "https://packagecontrol.io/channel_v3.json",
    ],
    ```
    * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
      you will not install this forked version of the package,
      but the original available on the Package Control default channel **`https://packagecontrol.io...`**
1. Now,
    go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    search for **`ConvertToUTF8`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.


Configuration
------------------
Please check ConvertToUTF8.sublime-settings file for details. You should save your personal settings in a file named "ConvertToUTF8.sublime-settings" under "User" folder. You can set project-specific settings (except encoding_list and max_cache_size) in the .sublime-project file which can be opened via "Project > Edit Project" menu.

* encoding_list: encoding selection list when detection is failed
* max_cache_size: maximum encoding cache size, 0 means no cache (default: 100)
* max_detect_lines: maximum detection lines, 0 means unlimited (default: 600)
* preview_action: converting the file's content to UTF-8 when previewing it (default: false)
* default_encoding_on_create: specific the default encoding for newly created file (such as "GBK"), empty value means using sublime text's "default_encoding" setting (default: "")
* convert_on_load: convert the file's content to UTF-8 when it is loaded (default: true)
* convert_on_save: convert the file's content from UTF-8 to its original (or specific) encoding when it is saved (default: true)
* convert_on_find: convert the text in Find Results view to UTF-8 (default: false)
* lazy_reload: save file to a temporary location, and reload it in background when switching to other windows or tabs (default: false)
* confidence: The minimum confidence rate which the converting will be performed automatic. (default: 0.95)

Usage
------------------
In most cases, this plug-in will take care of encoding issues automatically.

You can also use the "File > Set File Encoding to" menu entry to transform between different encodings. For example, you can open a UTF-8 file, and save it to GBK, and vice versa.

Note:
* if convert_on_save is set to `false`, the file will *NEVER* be saved to the selected encoding
* please do not edit the file before the encoding detection process is finished
* please try either increasing the value of max_detect_lines or set the encoding manually if the detection result is not accurate
* due to limitation of API, when lazy_reload is set to `true`, quit Sublime Text immediately after saving a file will cause the file to be saved as UTF-8, the correct content will be reload next time Sublime Text starts

Q & A
------------------
* Q: It is not working after installation, how do I fix it?

  A: Please try the following steps:
  1. Restart Sublime Text
  2. Make sure the plug-in folder is named "ConvertToUTF8" (skip this step if you install via "Package Control")
  3. See [Note section above](#note)
  4. Disable other encoding related plug-ins
  5. Contact me

* Q: Which encodings are supported?

  A: Any [encoding supported by Python](http://docs.python.org/library/codecs.html#standard-encodings) will be fine, other encodings like EUC-TW will not be supported.

* Q: Why does the content become a mess when the window is re-activated?

  A: This is caused by reloading and has been fixed, please update your *ConvertToUTF8* to latest version.

* Q: Why does ST2 ask me that file "Has changed on disk. Do you want to reload it?" when the window is re-activated.

  A: Same reason as above. Please choose "Cancel" if you have unsaved changes to the file.

* Q: When saving the file, Sublime Text tells me the file is saved as UTF-8, why?

  A: Don't worry, the plug-in will convert your file to original encoding.

* Q: My file was saved as UTF-8 and it's in a mess, how can I recover it?

  A: Please open the file and make sure its encoding is UTF-8, then choose the menu entry "File > Save with Encoding > Western (Windows 1252)", close and reopen this file.

Contact me
------------------
Please send me your questions or suggestions: sunlxy (at) yahoo.com or http://weibo.com/seanliang
