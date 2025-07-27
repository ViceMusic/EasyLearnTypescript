# 基本学习大纲

## 1. how to run a ts file？

Typescripts can't be directly interpreted as(beacuse) it is not a independent language, but rather a superset of Javascript.

That means all valid js codes remains functional within Ts programs.

The package of ts can be downloaded alternatively. For one, you can install Typescipt complier(tsc) via Node.js(ensure that it is pre-installed).

```
npm install -g typescipt
```

For this method, you can check whether successfully installing as below

```
npx tsc --version
```

By the way, npx is a convenient order provided by Nodejs, equaling to "./module/.bin/src"

And if you don't like this method, you can also choose another way: Installing bin package from offical website, then setting the **environment variables** in you computer.




0. getting-started/
安装 Node.js 与 TypeScript

初始化项目：tsc --init

配置 ESLint + Prettier（代码质量）

推荐编辑器与插件（如 VSCode）

1. basic-types/
number, string, boolean

array, tuple

enum

any, unknown, void, never

示例：基础类型声明、函数返回值限制

2. functions/
函数参数类型、默认值

可选参数、剩余参数

函数类型定义与表达式写法

this 问题（箭头函数 vs 普通函数）

3. object-types/
接口 (interface) vs 类型别名 (type)

可选属性、只读属性

类型扩展、交叉类型与联合类型

示例：设计一个简单用户系统接口定义

4. classes-and-oop/
类的基本语法：属性、构造函数、方法

public / private / protected

readonly 与 static

抽象类、接口实现、继承

示例：设计一个动物类的继承体系

5. generics/
泛型函数、泛型接口、泛型类

泛型约束（extends）、默认类型

示例：实现泛型工具函数，如 map, filter, queue 等

6. type-utils-and-advanced/
条件类型、映射类型、索引访问类型

keyof, infer, typeof, ReturnType, Partial, Pick 等

示例：封装一个表单校验器，利用高级类型推导出表单结构

7. module-system/
export / import 的使用

namespace 与 module 区别

配置 tsconfig 中的 paths, baseUrl

示例：分模块构建一个小型项目

8. tooling-and-integration/
Webpack + TS

Vite + TS

使用 TypeScript 编写 CLI 工具

示例：编写一个带参数解析的命令行工具（如自动生成 README）

9. real-world-practice/
用 TS 重写经典项目（如 TODO List）

创建一个 npm 包（比如一个 utils 库）

用 TS 编写 React/Vue 项目基础代码

示例：搭建一个完整的 React + TS 项目模板

10. appendix-and-notes/
常见错误汇总（如类型推导失败、any 泄漏）

推荐阅读资源：TypeScript 官网、TS Handbook、Effective TS

GitHub 上的优秀项目导航

技术实现建议
每个子文件夹都可包含：

README.md：说明本模块的核心知识点与案例

example.ts：示例代码

package.json（可选）：模块可独立运行

.vscode/launch.json：配好调试环境（加分项）