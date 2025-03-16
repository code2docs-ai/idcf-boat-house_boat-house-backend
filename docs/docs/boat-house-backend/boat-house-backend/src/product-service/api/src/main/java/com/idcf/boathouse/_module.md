# 基础信息

|      |      |
|------|------|
| 编码语言 | .java |
| 代码路径 | boat-house-backend/src/product-service/api/src/main/java/com/idcf/boathouse |
| 包名 | boat-house-backend.src.product-service.api.src.main.java.com.idcf.boathouse |
| 概述说明 | JdbcUtils类简化数据库操作，各类控制器管理加盟、菜品、订单等功能，BaseDao封装SQL执行，Spring Boot启动类初始化应用，Swagger配置生成API文档。 |

# 说明

JdbcUtils类简化数据库操作，支持增删改查和反射查询。多个控制器处理加盟、船坞故事、菜品、购物车、订单等功能，提供增删改查和流程管理。BaseController定义状态码和封装操作结果。多个实体类如OrderItemsVo、FoodCategoryPost、IntroPage等，描述订单项、食品类别、页面信息等。工具类如DateUtils、ActionResult、全局异常处理器、SpringContextHolder等，提供日期格式化、操作结果封装、异常处理和上下文管理。BaseDao封装SQL执行，简化数据库交互。Spring Boot启动类扫描Mapper包并启动应用。多个服务类如订单服务、IntroPageService、FoodService等，管理订单、页面、食品和购物车数据。Swagger配置类启用Swagger2，自动生成API文档。


### 包内部结构视图

```mermaid
graph TD
    product --> ProductServiceApplication.java
    product --> JdbcUtils.java
    product --> controller
    product --> enums
    product --> vo
    product --> models
    product --> untils
    product --> dao
    product --> dbentity
    product --> services
    product --> swagger
    product --> mapper
    controller --> JoinUsController.java
    controller --> IntroPageController.java
    controller --> FoodController.java
    controller --> BaseController.java
    controller --> ShopCartController.java
    controller --> BoatHouseController.java
    controller --> OrderController.java
    enums --> ResponseEnum.java
    enums --> OrderStatusEnum.java
    vo --> OrderItemsVo.java
    vo --> OrderItemsCreateVo.java
    vo --> OrderCreateVo.java
    vo --> OrderVo.java
    models --> FoodCategoryPost.java
    models --> IntroPage.java
    models --> OrderItems.java
    models --> FoodCategory.java
    models --> Orders.java
    models --> ShopCartPost.java
    models --> IntroPageFront.java
    models --> Food.java
    models --> FoodPost.java
    models --> constant
    models --> ShopCartPut.java
    models --> ShopCart.java
    models --> JoinUs.java
    models --> IntroPageValues.java
    constant --> OrderConstant.java
    untils --> DateUtils.java
    untils --> ActionResult.java
    untils --> GlobalExceptionHandler.java
    untils --> SpringContextHolder.java
    dao --> BaseDao.java
    dbentity --> IntroPageEntity.java
    services --> OrderService.java
    services --> IntroPageService.java
    services --> FoodService.java
    services --> ShopCartService.java
    services --> FoodCategoryService.java
    swagger --> SwaggerApp.java
    mapper --> OrderItemsMapper.java
    mapper --> IntroPageMapper.java
    mapper --> OrdersMapper.java
    mapper --> JoinUsMapper.java
```

该流程图展示了`product`模块的层级结构，包含多个子模块如`controller`、`enums`、`vo`、`models`等，每个子模块下又包含多个具体的文件或类。这些子模块和文件共同构成了`product`模块的完整功能结构，涵盖了从控制器到数据库实体、服务、工具类等多个方面的实现。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [product](product/_module.md) | package | JdbcUtils类简化数据库操作，各类控制器管理加盟、菜品、订单等功能，BaseDao封装SQL执行，Spring Boot启动类初始化应用，Swagger配置生成API文档。 |


