## 黄河文化知识图谱与大模型应用

### 项目说明

本项目旨在探索知识图谱与大模型的具体应用，整个系统由四个部分构成：

- 语音大模型，负责知识图谱的 QA 问答
- 图数据库，用于存储具体的知识
- 后端，连接图数据库，完成增删改查的业务，封装接口
- 前端，使用 vue2 + element ui 搭建，负责图谱展示和问答

### 知识图谱

根据语料构建知识图谱，展示黄河文化相关知识。

#### 详细节点设计

##### 诗人（Poet）

- **name**（名字）: 诗人的名字。
- **birthYear**（出生年）: 诗人的出生年份。
- **deathYear**（去世年）: 诗人的去世年份。
- **bio**（简介）: 关于诗人的详细生平介绍。
- **worksCount**（作品数量）: 诗人创作的作品总数。
- **influence**（影响）: 诗人对后世文化或诗歌的影响。

##### 诗作（Poem）

- **title**（标题）: 诗的标题。
- **content**（内容）: 诗的全文。
- **year**（年份）: 诗作创作的年份。
- **theme**（主题）: 诗的主要主题或情感。
- **background**（背景）: 诗作创作的背景或灵感来源。

##### 地点（Location）

- **name**（名称）: 地点的名称。
- **description**（描述）: 地点的详细描述。
- **importance**（重要性）: 地点在文化、历史或诗歌中的重要性。
- **relatedPoems**（相关诗作）: 与此地点相关的主要诗作列表。

### 大模型

模型使用 chatglm3-6b，结合 langchain 连接图数据库进行本地知识库搭建

### 后端设计

使用 springboot 搭建，遵循 mvc 架构

### 前端设计

使用 vue2 + element ui 搭建

```
|- components
  - AnswersDisplay.vue 展示大模型返回的答案
  - GraphStats.vue 展示图谱总体规模数据
  - NodeDetails.vue 展示节点具体信息
  - NodesList.vue 展示节点
  - SearchBar.vue 搜索框
|- App.vue
|- main.js
```
