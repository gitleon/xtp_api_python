中泰证券量化交易平台XTP PYTHON API接口

本项目是中泰证券XTP极速交易PYTHON接口的开源实现，供客户在量化交易中使用PYTHON接口快速接入XTP系统。中泰证券XTP是为股票交易而生的极速交易系统，为投资者提供极速交易、极速行情、Level2行情。

目前xtp系统最新的api版本为2.2.38.1，支持win、linux平台运行

请先到中泰证券xtp官方网站申请测试账号 https://xtp.zts.com.cn 及测试环境的连接ip、端口等信息

API参考官方C++版本的接口文档 https://xtp.zts.com.cn/doc/api/xtpDoc

由于python版本api封装使用的vs2010，如果未安装vs环境，运行时会提示ImportError:DLL load failed。需要根据python的位数选择对应的运行库，32位的选x86，64位选x64，执行程序参考文件包vs2010运行库
x86系统的vs2010运行库：vcredist_x86.exe
x64系统的vs2010运行库：vcredist_x64.exe 

##事项说明:

1.当前xtp的python api封装支持win7系统、win10系统和Linux系统，在bin目录下Linux文件夹中有python3封装库，Windows文件夹中有64位的python3封装库。test文件夹下包含行情和交易的测试脚本。

2.当前bin目录下编译时python3使用的python3.9.13版本，如果直接使用当前的封装库，请注意使用的python版本是否为3.9系列。在Windows下如果您使用的python版本和我们编译时使用的版本不一致，会导致调用python封装库失败。

3.如果您需要按自己的python版本编译封装库，可以使用source目录下的代码，根据自己的python的版本，及该python版本对应的编译后的boost库，自行编译所需的python封装库。（具体过程在doc文件夹下有编译过程文档，source文件夹下有源码，包括Linux和Windows下编译的python3封装库)。

4.XTP_API_20231031_2.2.38.1文件夹下存放最新的xtp系统的api，当前python封装库分别包含行情和交易库，python封装后的接口与当前xtp系统api的所有接口都保持一致，只有方法名有所区别，python封装后的接口方法名首字母小写，而xtp系统api的方法名首字母大写。因此所有封装后的python接口方法使用和功能都可以参见xtp系统api的接口方法。请在xtp_quote_api.h、xtp_trader_api.h两个头文件中了解各个接口的使用及功能。