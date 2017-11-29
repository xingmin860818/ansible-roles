## wayne Tomcat Deployment

- version：1.0.0
- Environment Ubuntu16.04 hosts

说明：
    该角色用于部署闪银环境的tomcat，默认tomcat版本号为8.0.45，

使用方法：
    1、上下线选择，可以设置tomcat部署或者下线，通过tomcat_operation参数设置,task/main.yml会
       根据配置选择执行的playbook,上下线请查看default/mail.yml文件进行初始配置。
    2、url下载包模式，需要提前制作下载链接
    3、jvm相关参数不一定符合所有需求，可以自行增加活删除配置内容。
    4、tomcat可以多实例部署，在default变量内填写对应的信息。
    4、其他：版本、项目名称、日志切割压缩日期、jvm相关参数可配置

	ansible-playbook -i hosts site.yml

tomcat部署路径：/data/services
业务日志路径: /data/logs
tomcat日志（gclog、dump）/data/services/tomcat-${project_name}-${port}/logs

tomcat下载地址(vpc内网)：http://ansible-resource.vpc100-oss-cn-beijing.aliyuncs.com/packages/tomcat-8.0.45.tar
playbook会通过端口自动检测配置tomcat是否在线上已存在
