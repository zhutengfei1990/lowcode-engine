---
title: workspace - 应用级 API
sidebar_position: 12
---

> **[@experimental](./#experimental)**<br/>
> **@types** [IPublicApiWorkspace](https://github.com/alibaba/lowcode-engine/blob/main/packages/types/src/shell/api/workspace.ts)<br/>
> **@since** v1.1.0

## 模块简介

通过该模块可以开发应用级低代码设计器。

## 变量

### isActive

是否启用 workspace 模式

### window

当前设计器窗口模型

```typescript
get window(): IPublicModelWindow
```

关联模型 [IPublicModelWindow](./model/window)

### plugins

应用级别的插件注册

```typescript
get plugins(): IPublicApiPlugins
```

关联模型 [IPublicApiPlugins](./plugins)

### windows

当前设计器的编辑窗口

```typescript
get window(): IPublicModelWindow[]
```

关联模型 [IPublicModelWindow](./model/window)

### resourceList

当前设计器的资源列表数据

```
get resourceList(): IPublicModelResource;
```

关联模型 [IPublicModelResource](./model/resource)

## 方法

### registerResourceType
注册资源

```typescript
/** 注册资源 */
registerResourceType(resourceTypeModel: IPublicTypeResourceType): void;
```

相关类型：[IPublicTypeResourceType](https://github.com/alibaba/lowcode-engine/blob/main/packages/types/src/shell/type/resource-type.ts)

### onChangeWindows

窗口新增/删除的事件

```typescript
function onChangeWindows(fn: () => void): void;
```

### onChangeActiveWindow

active 窗口变更事件

```typescript
function onChangeActiveWindow(fn: () => void): void;
```

### setResourceList

设置设计器资源列表数据

```typescript
setResourceList(resourceList: IPublicResourceList) {}
```

相关类型：[IPublicResourceOptions](https://github.com/alibaba/lowcode-engine/blob/main/packages/types/src/shell/type/resource-options.ts)

### onResourceListChange

设计器资源列表数据变更事件

```typescript
onResourceListChange(fn: (resourceList: IPublicResourceList): void): (): void;
```

相关类型：[IPublicResourceOptions](https://github.com/alibaba/lowcode-engine/blob/main/packages/types/src/shell/type/resource-options.ts)

### openEditorWindow

打开视图窗口

```typescript
openEditorWindow(resourceName: string, title: string, options: Object, viewName?: string): void;
```

### openEditorWindowById

通过视图 id 打开窗口

```typescript
openEditorWindowById(id: string): void;
```

### removeEditorWindow

移除视图窗口

```typescript
removeEditorWindow(resourceName: string, title: string): void;
```

### removeEditorWindowById

通过视图 id 移除窗口

```typescript
removeEditorWindowById(id: string): void;
```