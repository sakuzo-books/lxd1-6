# 正誤情報

## 初版

* P26 : 4.4 Sambaをインストールする  
  `yum` コマンドが間違っている  
  
  * 誤
  ```
  [root@centos7-smb61 ~]# 
  [root@centos7-smb61 ~]# yum search samba
  [root@centos7-smb61 ~]# 
  ```

  * 正
  ```
  [root@centos7-smb61 ~]# 
  [root@centos7-smb61 ~]# yum install -y samba
  [root@centos7-smb61 ~]# 
  ```

* P68 : 8.4 ロードバランサーの設定変更  
  `access_log` でログフォーマットの指定が間違っている  
  
  * 誤
  ```
  [root@centos7-lb31 conf.d]# vi drive.example.co.jp.conf
  upstream centos7-nc {
      server 192.168.56.81;
  }
  server {
      listen 80;
      server_name drive.example.co.jp;
      access_log /var/log/nginx/access.log upstreamlog;
      location / {
          proxy_set_header Host $host;
          proxy_pass http://centos7-nc;
      }
  }
  [root@centos7-lb31 conf.d]#
  ```

  * 正
  ```
  [root@centos7-lb31 conf.d]# vi drive.example.co.jp.conf
  upstream centos7-nc {
      server 192.168.56.81;
  }
  server {
      listen 80;
      server_name drive.example.co.jp;
      access_log /var/log/nginx/access.log main;
      location / {
          proxy_set_header Host $host;
          proxy_pass http://centos7-nc;
      }
  }
  [root@centos7-lb31 conf.d]#
  ```

* P92 : 9.2 Sambaの設定変更をする  
  smb.conf の `ldap group suffix` の指定が間違っている  
  
  * 誤
  ```
  [global]
            ：
          ldap group suffix = ou=Groupss
            ：
  ```

  * 正
  ```
  [global]
            ：
          ldap group suffix = ou=Groups
            ：
  ```


* P104 : 9.5 バックエンドデータベースを切り替える  
  smb.conf の `ldap group suffix` の指定が間違っている  
  
  * 誤
  ```
  [global]
            ：
          ldap group suffix = ou=Groupss
            ：
  ```

  * 正
  ```
  [global]
            ：
          ldap group suffix = ou=Groups
            ：
  ```
