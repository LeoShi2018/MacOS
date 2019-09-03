## pipenv 国内源修改

#### 1. 修改Pipfile

> 文件存放路径:Pycharm项目路径根下面

````
$ vi /Users/LeoShi/Dropbox/GitHub/QuantitativeTrading/Pipfile
[[source]]
name = "pypi"
-----修改下面的链接-------------------------
url = "https://pypi.org/simple"
verify_ssl = true

[dev-packages]

[packages]

[requires]
python_version = "3.5"
````
> 阿里云：http://mirrors.aliyun.com/pypi/simple/
>
> 豆瓣：http://pypi.douban.com/simple/
>
> 清华大学：https://pypi.tuna.tsinghua.edu.cn/simple/
>
> 中国科学技术大学：https://pypi.mirrors.ustc.edu.cn/simple/

````
://pypi.org/simple[source]]
name = "pypi"
url = "https://pypi.tuna.tsinghua.edu.cn/simple/"
verify_ssl = true

[dev-packages]

[packages]

[requires]
python_version = "3.5"
````

## END