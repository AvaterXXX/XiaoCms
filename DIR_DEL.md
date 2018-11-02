# DIR_DEL
---------------
There is a data backup here, and it is easy to have a vulnerability in this place.
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/dirdel_1.png)
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/dirdel_2.png)

After selecting the backup and clicking delete in batches, you can capture the package and see it.
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/dirdel_3)
Can be seen in the `database.php`, call the import method, This function is located `XiaoCms\admin\controller\database.php`.

![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/dirdel_4.png)
The line is the key, you can see that there is no restriction on our input, which means you can use `../` etc, so there is any directory deletion here.

![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/dirdel_5.png)
First create a new directory in the root directory.The submitted path is `../../1`
![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/dirdel_6.png)
