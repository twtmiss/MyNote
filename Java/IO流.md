### IO流

- 字节流读取文件
  - 使用FileInputStream读取文件
  - 使用InputStreamReader将字节流转为字符流
  - 使用BufferReader从缓冲区内将字符流信息打印出来
  - 调用BufferReader的close方法关闭
- 字符流读取文件
  - 使用FileReader将文件读取到缓冲区
  - 使用BufferReader从缓冲区内将字符流信息打印出来
  - 调用BufferReader的close方法关闭