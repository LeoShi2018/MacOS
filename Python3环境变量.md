## Python3 环境变量配置

````
cat >> ~/.bash_profile <<EOF
alias python="/Library/Frameworks/Python.framework/Versions/3.7/bin/python3.7"
EOF

source ~/.bash_profile

bogon:~ LeoShi$ python -V
------------------------------
Python 3.7.4
````

## END