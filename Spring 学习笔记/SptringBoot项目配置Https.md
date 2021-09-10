# SpringBoot项目配置Https

- 使用keytool命令生成证书
- 在当前目录下生成keystore.p12证书库，且证书名称为tomcat
  
- `keytool -genkey -alias tomcat -dname "CN=Andy,OU=kfit,O=kfit,L=HaiDian,ST=BeiJing,C=CN" -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore keystore.p12 -validity 365`
  
- springBoot配置

- application.yml文件配置

  ```
  ssl:
    protocol: TLS
    key-store: /Users/twtmiss/杂七杂八的东西/keystore.p12
    key-store-password: twtmiss
    keyStoreType: PKCS12
    keyAlias: tomcat
  ```


- 如此配置完成