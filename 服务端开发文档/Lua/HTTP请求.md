外部工具推荐：需要架设 Httppost自定义数据传输推荐使用：http://httppost.cn/ (非官方).
(相关产品由第三方提供，996引擎方不负责售前售后服务，请用户自行甄别选择)

HTTP请求

httppost

注意：不提供回调函数与返回值

参数	类型	空	默认	注释
url	string	否		链接地址
suffix	string	否		请求信息
head	json字符串格	否		请求头
示例
    httppost("http://localhost/php/test.php",'{token:mir200post}','{Host:system}')


debug日志
{
    "server":{
        "PATH":"C:\\Program Files (x86)\\Common Files\\Oracle\\Java\\javapath;F:\\VMware\\bin\\;C:\\Windows\\system32;C:\\Windows;C:\\Windows\\System32\\Wbem;C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\;C:\\Windows\\System32\\OpenSSH\\;C:\\Program Files\\TortoiseSVN\\bin;C:\\Microsoft VS Code\\bin;C:\\Program Files (x86)\\GtkSharp\\2.12\\bin;C:\\Program Files (x86)\\Windows Kits\\8.1\\Windows Performance Toolkit\\;C:\\Program Files\\Microsoft SQL Server\\110\\Tools\\Binn\\;C:\\Program Files (x86)\\Microsoft SDKs\\TypeScript\\1.0\\;C:\\Program Files\\Microsoft SQL Server\\120\\Tools\\Binn\\;C:\\Users\\admin\\AppData\\Local\\Programs\\Python\\Python39\\Scripts\\;C:\\Users\\admin\\AppData\\Local\\Programs\\Python\\Python39\\;C:\\Cocos\\Cocos2d-x\\Cocos2d-x-3.10\\templates;C:\\Cocos\\Cocos2d-x\\Cocos2d-x-3.10\\tools\\cocos2d-console\\bin;C:\\Users\\admin\\AppData\\Local\\Microsoft\\WindowsApps",
        "SYSTEMROOT":"C:\\Windows",
        "COMSPEC":"C:\\Windows\\system32\\cmd.exe",
        "PATHEXT":".COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC",
        "WINDIR":"C:\\Windows",
        "PHPRC":"F:\/php\/phpstudy_pro\/Extensions\/php\/php7.3.4nts",
        "_FCGI_SHUTDOWN_EVENT_":"8968",
        "HTTP_CONNECTION":"close",
        "SCRIPT_NAME":"\/php\/test.php",
        "REQUEST_URI":"\/php\/test.php",
        "QUERY_STRING":"",
        "REQUEST_METHOD":"POST",
        "SERVER_PROTOCOL":"HTTP\/1.1",
        "GATEWAY_INTERFACE":"CGI\/1.1",
        "REMOTE_PORT":"49742",
        "SCRIPT_FILENAME":"F:\/php\/phpstudy_pro\/WWW\/php\/test.php",
        "SERVER_ADMIN":"admin@example.com",
        "CONTEXT_DOCUMENT_ROOT":"F:\/php\/phpstudy_pro\/WWW",
        "CONTEXT_PREFIX":"",
        "REQUEST_SCHEME":"http",
        "DOCUMENT_ROOT":"F:\/php\/phpstudy_pro\/WWW",
        "REMOTE_ADDR":"::1",
        "SERVER_PORT":"80",
        "SERVER_ADDR":"::1",
        "SERVER_NAME":"system",
        "SERVER_SOFTWARE":"Apache\/2.4.39 (Win64) OpenSSL\/1.1.1b mod_fcgid\/2.3.9a mod_log_rotate\/1.02",
        "SERVER_SIGNATURE":"",
        "SystemRoot":"C:\\Windows",
        "HTTP_CACHE_CONTROL":"no-cache",
        "CONTENT_LENGTH":"16",
        "HTTP_USER_AGENT":"Microsoft Internet Explorer",
        "HTTP_HOST":"system",
        "CONTENT_TYPE":"application\/x-www-form-urlencoded",
        "FCGI_ROLE":"RESPONDER",
        "PHP_SELF":"\/php\/test.php",
        "REQUEST_TIME_FLOAT":1688001980.321139,
        "REQUEST_TIME":1688001980
    },
    "files":[

    ],
    "post":{
        "token":"mir200post"
    },
    "tokenn":"996633",
    "get":[

    ],
    "input":null
}