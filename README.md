# categraf-playbook
`ansible-playbook` for [categraf](https://github.com/flashcatcloud/categraf)

## 功能
* 批量在主机上使用docker-compose部署categraf
* 支持基础系统指标的采集
* 支持不同主机差异化配置的指标采集(如端口监控等)
* 幂等操作

## 如何使用
* 配置`roles/categraf/defaults/main.yaml`中的变量
* 配置`hosts`文件中的主机
* 运行`ansible-playbook -i hosts -f categraf.yaml`
* `have fun`

## Q&A
### 如何添加采集插件?
* 对于通用的采集插件，将插件配置放入`roles/categraf/templates/conf`中，文件名需要为`插件名`+`.toml`
* 对于主机个性化插件，支持通过`主机变量` + `jinja2-template`的方式渲染个性化配置，可以参考`roles/categraf/templates/conf/net_response.toml.j2`


