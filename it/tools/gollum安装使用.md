

## 错误处理
### Encoding::CompatibilityError at /create
#### 安装gollum-regged_adapter
下面的错误是因为没有cmake，安装cmake就可以了
```
 $gem install gollum-rugged_adapter
Building native extensions.  This could take a while...
ERROR:  Error installing gollum-rugged_adapter:
	ERROR: Failed to build gem native extension.

    current directory: /usr/local/lib/ruby/gems/2.3.0/gems/rugged-0.25.1.1/ext/rugged
/usr/local/opt/ruby/bin/ruby -r ./siteconf20170625-70503-8x0eb6.rb extconf.rb
checking for gmake... no
checking for make... yes
checking for cmake... no
ERROR: CMake is required to build Rugged.
*** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of necessary
libraries and/or headers.  Check the mkmf.log file for more details.  You may
need configuration options.

Provided configuration options:
	--with-opt-dir
	--with-opt-include
	--without-opt-include=${opt-dir}/include
	--with-opt-lib
	--without-opt-lib=${opt-dir}/lib
	--with-make-prog
	--without-make-prog
	--srcdir=.
	--curdir
	--ruby=/usr/local/Cellar/ruby/2.3.3/bin/$(RUBY_BASE_NAME)
	--use-system-libraries

To see why this extension failed to compile, please check the mkmf.log which can be found here:

  /usr/local/lib/ruby/gems/2.3.0/extensions/x86_64-darwin-16/2.3.0/rugged-0.25.1.1/mkmf.log

extconf failed, exit code 1

Gem files will remain installed in /usr/local/lib/ruby/gems/2.3.0/gems/rugged-0.25.1.1 for inspection.
Results logged to /usr/local/lib/ruby/gems/2.3.0/extensions/x86_64-darwin-16/2.3.0/rugged-0.25.1.1/gem_make.out
greenfoam@MacBook:~/git/mydata.wiki$ brew --hel
Error: Unknown command: --hel
greenfoam@MacBook:~/git/mydata.wiki$ brew --help
Example usage:
  brew search [TEXT|/REGEX/]
  brew (info|home|options) [FORMULA...]
  brew install FORMULA...
  brew update
  brew upgrade [FORMULA...]
  brew uninstall FORMULA...
  brew list [FORMULA...]

Troubleshooting:
  brew config
  brew doctor
  brew install -vd FORMULA

Developers:
  brew create [URL [--no-fetch]]
  brew edit [FORMULA...]
  http://docs.brew.sh/Formula-Cookbook.html

Further help:
  man brew
  brew help [COMMAND]
  brew home
```
[参考](https://segmentfault.com/q/1010000002377107)
#### 下面的方法没有鸟用，可能是适合之前的版本
```
vi /usr/local/Cellar/ruby/2.3.3/lib/ruby/2.3.0/erb.rb
s.force_encoding(enc)##添加一行文件
```

[参考文件](http://blog.163.com/xingchao_gan/blog/static/183374228201186101653701/)