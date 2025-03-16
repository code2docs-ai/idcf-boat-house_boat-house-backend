# 基础信息

|      |      |
|------|------|
| 编码语言 | .java |
| 代码路径 | boat-house-backend/src/product-service/api/src/main/java/com/idcf/boathouse/product/services/IntroPageService.java |
| 包名 | com.idcf.boathouse.product.services |
| 依赖项 | ['com.idcf.boathouse.product.mapper.IntroPageMapper', 'com.idcf.boathouse.product.models.IntroPage', 'com.idcf.boathouse.product.models.IntroPageFront', 'com.idcf.boathouse.product.models.IntroPageValues', 'org.springframework.beans.factory.annotation.Autowired', 'org.springframework.stereotype.Service', 'java.util.Date', 'java.util.List'] |
| 概述说明 | IntroPageService类管理船坞故事的增删改查操作。 |

# 说明

IntroPageService类是一个用于管理船坞故事数据的服务类，提供了插入、更新、删除和获取船坞故事数据的功能。该类通过这些操作实现对船坞故事数据的全面管理，确保数据的完整性和一致性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| IntroPageService | class | IntroPageService类提供插入、更新、删除和获取船坞故事数据的功能。 |



## 类 IntroPageService

|      |      |
|------|------|
| 访问范围 | @Service;public |
| 类型 | class |
| 名称 | IntroPageService |
| 说明 | IntroPageService类提供插入、更新、删除和获取船坞故事数据的功能。 |


### UML类图

```mermaid
classDiagram
    class IntroPageService {
        -IntroPageMapper introPageMapper
        +inserIntroPage(IntroPageFront introPageFront) void
        +deleteIntroPage(String page_id) void
        +updateIntroPage(IntroPageFront introPageFront) void
        +getIntroPage(String page_id) IntroPageFront
    }

    class IntroPageMapper {
        +findIntroPage(String page_id) List~IntroPage~
        +updateById(IntroPage introPage) void
        +insert(IntroPage introPage) void
    }

    class IntroPage {
        -String pageId
        -String pageTitle
        -String pageApiUrl
        -String image
        -String text
        -boolean deleted
        -Date updateTime
        +getPageId() String
        +setPageId(String pageId) void
        +getPageTitle() String
        +setPageTitle(String pageTitle) void
        +getPageApiUrl() String
        +setPageApiUrl(String pageApiUrl) void
        +getImage() String
        +setImage(String image) void
        +getText() String
        +setText(String text) void
        +isDeleted() boolean
        +setDeleted(boolean deleted) void
        +getUpdateTime() Date
        +setUpdateTime(Date updateTime) void
    }

    class IntroPageFront {
        -String page_id
        -String page_title
        -String page_api_url
        -IntroPageValues page_values
    }

    class IntroPageValues {
        -String text
        -String image
    }

    IntroPageService --> IntroPageMapper : 依赖
    IntroPageMapper --> IntroPage : 依赖
    IntroPageFront --> IntroPageValues : 依赖
```

**描述：**
`IntroPageService` 是一个服务类，负责处理与 `IntroPage` 相关的业务逻辑，包括插入、更新、删除和获取 `IntroPage` 数据。它依赖于 `IntroPageMapper` 来进行数据库操作。`IntroPage` 类表示数据库中的实体，包含页面ID、标题、API URL、图片、文本等属性。`IntroPageFront` 和 `IntroPageValues` 类用于前端数据的传递和展示。整个类图展示了服务层与数据访问层之间的依赖关系，以及数据实体的结构。


### 内部方法调用关系图

```mermaid
graph TD
    A["类IntroPageService"]
    B["属性: IntroPageMapper introPageMapper"]
    C["方法: inserIntroPage(IntroPageFront introPageFront)"]
    D["方法: deleteIntroPage(String page_id)"]
    E["方法: updateIntroPage(IntroPageFront introPageFront)"]
    F["方法: getIntroPage(String page_id)"]
    G["调用: introPageMapper.findIntroPage(page_id)"]
    H["判断: lstIntroPage!=null && lstIntroPage.size()>0"]
    I["更新: introPageMapper.updateById(introPage)"]
    J["插入: introPageMapper.insert(introPage)"]
    K["抛出异常: throw new Exception('未能根据page_id找到对应的故事数据')"]
    L["返回: IntroPageFront对象"]
    M["返回: null"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    C --> G
    C --> H
    H --> I
    H --> J
    D --> G
    D --> H
    H --> I
    H --> K
    E --> G
    E --> H
    H --> I
    H --> K
    F --> G
    F --> H
    H --> L
    H --> M
```

这段代码定义了一个`IntroPageService`类，用于管理船坞故事的插入、更新、删除和查询操作。类中通过`IntroPageMapper`与数据库交互，根据传入的`IntroPageFront`对象或`page_id`执行相应的操作。如果数据存在，则更新或删除；如果不存在，则插入或抛出异常。查询操作返回`IntroPageFront`对象或`null`。流程图展示了各个方法的调用关系和判断逻辑。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| introPageMapper | IntroPageMapper | 自动注入IntroPageMapper实例。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| deleteIntroPage | void | 根据page_id删除介绍页，若未找到则抛出异常。 |
| getIntroPage | IntroPageFront | 通过page_id获取IntroPageFront对象，包含页面ID、标题、API URL及内容。 |
| inserIntroPage | void | 插入或更新介绍页信息，包括标题、API链接、图片和文本。 |
| updateIntroPage | void | 更新介绍页信息，若找到对应数据则修改并保存，否则抛出异常。 |




