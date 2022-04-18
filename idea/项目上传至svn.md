
**确保项目的版本控制没有开启**

![[Pasted image 20220301110739.png]](assest/Pasted image 20220301110739.png)



**首先如果开启了，就先关闭它**

**在项目下的.idea文件夹中找到vcs.xml，直接删除**
![[Pasted image 20220301110546.png]](assest/Pasted image 20220301110546.png)

**查看项目根目录看有没有.svn或.git文件夹，如果有就删除**
![[Pasted image 20220301113016.png]](assest/Pasted image 20220301113016.png)

**打开VCS菜单，点击Share Project(Subversion)**
![[Pasted image 20220301113112.png]](assest/Pasted image 20220301113112.png)

**选择要上传到的svn目录**

这里上传到 `https://192.168.0.50/svn/HaierPVmonitor/02DevelopmentArea/04 编码实现/`

![[Pasted image 20220301113332.png]](assest/Pasted image 20220301113332.png)

**点击OK，如果多个可选，选最新的就行**
![[Pasted image 20220301113520.png]](assest/Pasted image 20220301113520.png)

**操作完成**
![[Pasted image 20220301113613.png]](assest/Pasted image 20220301113613.png)

在svn选项卡中就有了svn信息，在commit中正常提交文件即可
![[Pasted image 20220301113702.png]](assest/Pasted image 20220301113702.png)