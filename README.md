# MD5暴力破解
使用python的多进程与多线程暴力破解md5  
分为以下步骤
- 将可能的长度枚举出来，存入队列
- 根据长度，枚举出所有的可能的字符串
- 将字符串加入一个task队列，此处使用的是多进程策略，每一个进程只有一个线程
- 从task队列中读取字符串，并进行md5验证，此处使用多核多线程，每一个进程内的线程可以设置
- 如果找到字符串，则加入result队列，一旦加入，程序将立即终止所有进程，并输出答案
