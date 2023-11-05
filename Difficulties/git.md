# 1. git push 报错 remote Support for password authentication was removed on August 13, 2021.
**时间**：2023.10.15  
**描述**：  

```
$ git push
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/Hi-SophiaXu/StudyNotes.git/'
```
**原因**：  
自2021.8.13后不再支持用户名密码的方式验证了，需要创建个人访问令牌（personal access token）  

**解决**：  
GitHub : Settings/Developer Settings/Personal access tokens/Tokens
```
git remote set-url origin https://[your_accessToken]@github.com/[username]/[repo].git
```
**参考**：[CSDN|解决 remote Support for password authentication was removed on August 13, 2021.](https://blog.csdn.net/qq_50840738/article/details/125087816?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169734424516777224493825%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169734424516777224493825&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-125087816-null-null.142^v96^pc_search_result_base8&utm_term=remote%3A%20Support%20for%20password%20authentication%20was%20removed%20on%20August%2013%2C%202021.&spm=1018.2226.3001.4187)





# 2. git push 报错 fatal: The remote end hung up unexpectedly
**时间**：2023.10.15  
**描述**：

```
$ git push
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 20 threads
Compressing objects: 100% (11/11), done.
error: RPC failed; HTTP 403 curl 22 The requested URL returned error: 403
fatal: the remote end hung up unexpectedly
Writing objects: 100% (13/13), 463.33 MiB | 49.69 MiB/s, done.
Total 13 (delta 3), reused 0 (delta 0), pack-reused 0
fatal: the remote end hung up unexpectedly
Everything up-to-date
```
**原因**：  
推送的文件太大
**解决**：  
1. 修改设置 git config 文件的 postBuffer 的大小。（设置为500MB）  
```
# 或更大1048576000
git config --local http.postBuffer 524288000
```
2. 直接修改本地仓库的 .config 文件
```
[http]
	postBuffer = 524288000
```
**参考**：[CSDN|Git：解决报错：fatal: The remote end hung up unexpectedly](https://blog.csdn.net/u013250071/article/details/81203900?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169736148016800182170359%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169736148016800182170359&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-81203900-null-null.142^v96^pc_search_result_base8&utm_term=fatal%3A%20the%20remote%20end%20hung%20up%20unexpectedly&spm=1018.2226.3001.4187)