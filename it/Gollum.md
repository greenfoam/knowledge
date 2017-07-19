[[_TOC_]]

## 简介
gollum是一个轻量级的wiki系统，使用[git](Git)同步到你想要同步的服务器，github、gitlab均使用此系统

## SYSTEM REQUIREMENTS

| Operating System | Ruby                               | Adapters         | Supported |
| ---------------- | ---------------------------------- | ---------------- | --------- |
| Unix/Linux-like  | Ruby 1.9.3+                        | all except       | RJGit     |
| Unix/Linux-like  | JRuby (1.9.3+ compatible)          | RJGit            | yes       |
| Windows          | [Ruby](ruby) 1.9.3+                | all except RJGit | no        |
| Windows          | [JRuby](jruby) (1.9.3+ compatible) | RJGit            | almost1   |


## 安装
在[gollum主页](https://github.com/gollum/gollum)上有介绍.

### MAC安装步骤：

1. `gem install gollum`
2. `$gem install gollum-rugged_adapter`

### window安装步骤

1. 安装[jruby](jruby)

2. 打开cmd 安装gollum


    `gem install gollum`

3. 安装[gollum-rugged_adapter](https://rubygems.org/gems/gollum-rugged_adapter/versions/0.4.4)
    `gem install gollum-rugged_adapter`




## 运行
在wiki目录运行 `gollum`命令，`gollum --adapter rugged`

## 使用
语法与标准[markdown](markdown)有一些区别，下面是发现的一些区别（逐步完善中）：

- 目录 
```markdown
[[_TOC_]]  #ps:这条需要这样写：```markdown
```

## 错误处理

### 搜索功能错误——待解决
使用adapter，在MAC系统下搜索功能错误。在windows下，未使用adapter，搜索功能也报错

### Encoding::CompatibilityError at /create

#### 安装gollum-regged_adapter

下面的错误是因为没有[cmake](CMake)，安装[cmake](cmake)就可以了
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

## 参考资料

### 介绍了如何使用apache 发布pollum
<https://jingxin.me/blog/blog/2012/07/12/ti-yan-gollum/>

### 使用这个方法解决了问题
<https://segmentfault.com/q/1010000002377107>

### 下面的方法没有鸟用，可能是适合之前的版本
```
vi /usr/local/Cellar/ruby/2.3.3/lib/ruby/2.3.0/erb.rb
s.force_encoding(enc)##添加一行文件
```
<http://blog.163.com/xingchao_gan/blog/static/183374228201186101653701/>