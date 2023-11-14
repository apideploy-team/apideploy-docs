### 文档生成原理

Apideploy推崇**文档即代码**的设计理念，所以作者**强烈推荐基于代码注释的文档生成方式**，它不像**swagger**的实现那么笨重。

#### 基于代码注释生成文档

基于代码注释生成文档，Apideploy的实现参考并依赖了[smart-doc](https://github.com/TongchengOpenSource/smart-doc)的开源代码，smart-doc是一款基于[qdox](https://github.com/paul-hammant/qdox)优秀的Java文档解析工具，它很方便的实现了基于代码注释到API文档的过程。

在实际的应用场景中，作者发现smart-doc存在一些小问题，比如smart-doc采用maven plugin的方式来生成文档，但难以避免项目无法正常运行而文档却生成成功，最后可能会出现接口上的不一致；smart-doc生成的离线文档在交互视觉上个人觉得有改善空间，且不具备debug的能力，缺少示例代码、字段校验描述等。

以上种种，Apideploy开源了[Java代码注释的文档生成client](https://github.com/apideploy-team/apideploy-jakarta-client)，其系统架构参考：[产品介绍](../getting-started/apideploy-overview.md)

#### 基于Swagger / OpenAPI的文档生成

在基于Java Web项目开发的Swagger实现中，目前用的比较多的开源实现是[Springfox](https://github.com/springfox/springfox)(包括国内的[Knife4j](https://doc.xiaominfo.com/))与[Springdoc-openapi](https://github.com/springdoc/springdoc-openapi)。Springfox的用户较多，但貌似已经停止更新，已经不再支持springboot3.0+的项目。

Apideploy兼容了springfox和springdoc-openapi的全部实现，所以如果之前的项目使用的是swagger项目，也非常方便切换到Apideploy进行文档托管和测试。

