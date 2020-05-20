# PWM 是一个管理prometheus alertmanager的统一管理平台

包含功能:
  1. 管理prometheus的配置
  2. 管理exporter
  3. 管理报警规则的配置
  4. 支持报警分组
  5. 支持邮件 短信 企业微信报警
  6. 配置之间用服务树方式展现
  7. 报警历史记录查询
  8. 报警静默配置

此平台优点:
  1. 支持用户组管理
  2. 通过服务树，清晰的展示数据源 报警规则 报警附属配置之间的关系
  3. 支持静默配置
  4. 支持自定义报警方式 如 短信 微信 邮件报警
  5. 减少操作人员学习成本
  6. 支持记录展示报警历史
  7. 操作管理方便 快捷
  
此平台架构图：（图中画红框的为此平台所需架构）
  django framework + vue-cli + consul + confd + prometheus + alertmanager
  其中exporter会以服务的方式注册到consul中，confd服务管理prometheus rules alertmanager的配置文件
![Image text](https://github.com/starjoe/PWM/blob/master/img-folder/prometheus.png?raw=true)
  
PWM 功能列表


![image text](https://github.com/starjoe/PWM/blob/master/img-folder/pwm2.png?raw=true)

PWM dashboard
![Image text](https://github.com/starjoe/PWM/blob/master/img-folder/dashboard.png?raw=true)

PWM 报警规则
![Image text](https://github.com/starjoe/PWM/blob/master/img-folder/rules1.png?raw=true)
![Image text](https://github.com/starjoe/PWM/blob/master/img-folder/rules2.png?raw=true)

PWM 静默管理
![image text](https://github.com/starjoe/PWM/blob/master/img-folder/silence.png?raw=true)
![image text](https://github.com/starjoe/PWM/blob/master/img-folder/silence2.png?raw=true)

# 安装部署

python-2.7.5 Django-1.11.22 djangorestframework-3.9.4 node-v10.15.0 npm-6.4.1

1. 后端安装
  cd PWM/  
  pip install -r requirements.txt  
  python manage.py makemigrations  
  python manage.py migrate  
  python manage.py runserver 0.0.0.0:888
  
2. 前端安装
  前端代码地址
  [PWM-web](https://github.com/starjoe/PWM-web)
  
  部署需要安装node npm  
  注： 在启动服务之前，cd PWM-web && grep -R 10.50.182.65 \*, 把文件中的ip地址修改成你后端服务的ip地址   
  npm install -g @vue/cli  
  cd PWM-web/jy_cmdb_vue  
  npm run dev  
  
  
  
