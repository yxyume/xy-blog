python \> pyinstaller
=

# pyinstaller打包python程序    
More Info	https://blog.csdn.net/Roanlys/article/details/80951185<br>


1.pyinstaller打包exe文件时，递归太深：RecursionError: maximum recursion depth exceeded。<br>
第一步：使用pyi-makespec [option] name.py，生成name.spec文件。（这里，我的name.py是control_gui.spec）    \#Cite:    https://pyinstaller.readthedocs.io/en/stable/spec-files.html<br>
第二步：将以下代码添加到上面生成的spec文件中。<br>
```
    import sys
    sys.setrecursionlimit(5000)#5000这个数字可以随便设
```
第三步：使用pyinstaller [option] name.spec进行打包。<br>

2.使用了tensorflow，然后对应的pandas版本不正确，才导致了错误。错误是：type object 'pandas._libs.tslibs.conversion._TSObject'has no attribute '_reduce_cython__'。<br>
用的python版本是3.X是一个原因，其中一个重要的原因是我的Pandas版本是0.23.0，应该把安装0.20.0版本。因此，我把pandas版本使用pip install pandas==0.20.0安装之后，问题就解决了！<br>

