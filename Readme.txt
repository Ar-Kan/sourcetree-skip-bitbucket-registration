How to skip bitbucket registration when installing sourcetree?

The first step is to run SourceTreeSetup-3.1.3.exe and close it after popping up the registration interface.

The second step is to open the %LocalAppData%\Atlassian directory, find accounts.json and user.config, and replace them with the files I provided.

e.g.
%LocalAppData%\Atlassian\SourceTree\accounts.json
%LocalAppData%\Atlassian\SourceTree.exe_Url_iayhtc13zv3obzuz5vchezjs1az2q5ef\3.1.3.3158\user.config


Configurations to work with local Git server and remote Git server:

In SourceTree Options->Network check:
    Use default operating system settings
    Proxy server requires username and password
    Add proxy server configuration to Git / Mercurial

Add in %USERPROFILE%\.gitconfig
[http]
    sslVerify = true
    proxy = http://my.proxy.net:8080
[https]
    sslVerify = true
    proxy = http://my.proxy.net:8080
[http "http://my.internalGitServer.com"]
    sslVerify = false
