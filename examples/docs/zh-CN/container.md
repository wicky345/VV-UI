<style>
  .ox-header, .ox-footer {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  
  .ox-aside {
    color: #333;
  }
  
  #chang-jian-ye-mian-bu-ju + .demo-container {
    .ox-header, .ox-footer {
      text-align: center;
    }
  
    .ox-aside {
      background-color: #D3DCE6;
      text-align: center;
      line-height: 200px;
    }
  
    .ox-main {
      background-color: #E9EEF3;
      color: #333;
      text-align: center;
      line-height: 160px;
    }
    
    & > .source > .ox-container {
      margin-bottom: 40px;
    
      &:nth-child(5) .ox-aside,
      &:nth-child(6) .ox-aside {
        line-height: 260px;
      }

      &:nth-child(7) .ox-aside {
        line-height: 320px;
      }
    }
  }
</style>

<script>
  export default {
    data() {
      const item = {
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      };
      return {
        tableData: Array(20).fill(item)
      }
    }
  };
</script>

## Container 布局容器
用于布局的容器组件，方便快速搭建页面的基本结构：

`<ox-container>`：外层容器。当子元素中包含 `<ox-header>` 或 `<ox-footer>` 时，全部子元素会垂直上下排列，否则会水平左右排列。

`<ox-header>`：顶栏容器。

`<ox-aside>`：侧边栏容器。

`<ox-main>`：主要区域容器。

`<ox-footer>`：底栏容器。

:::tip
以上组件采用了 flex 布局，使用前请确定目标浏览器是否兼容。此外，`<ox-container>` 的子元素只能是后四者，后四者的父元素也只能是 `<ox-container>`。
:::

### 常见页面布局

:::demo
```html
<ox-container>
  <ox-header>Header</ox-header>
  <ox-main>Main</ox-main>
</ox-container>

<ox-container>
  <ox-header>Header</ox-header>
  <ox-main>Main</ox-main>
  <ox-footer>Footer</ox-footer>
</ox-container>

<ox-container>
  <ox-aside width="200px">Aside</ox-aside>
  <ox-main>Main</ox-main>
</ox-container>

<ox-container>
  <ox-header>Header</ox-header>
  <ox-container>
    <ox-aside width="200px">Aside</ox-aside>
    <ox-main>Main</ox-main>
  </ox-container>
</ox-container>

<ox-container>
  <ox-header>Header</ox-header>
  <ox-container>
    <ox-aside width="200px">Aside</ox-aside>
    <ox-container>
      <ox-main>Main</ox-main>
      <ox-footer>Footer</ox-footer>
    </ox-container>
  </ox-container>
</ox-container>

<ox-container>
  <ox-aside width="200px">Aside</ox-aside>
  <ox-container>
    <ox-header>Header</ox-header>
    <ox-main>Main</ox-main>
  </ox-container>
</ox-container>

<ox-container>
  <ox-aside width="200px">Aside</ox-aside>
  <ox-container>
    <ox-header>Header</ox-header>
    <ox-main>Main</ox-main>
    <ox-footer>Footer</ox-footer>
  </ox-container>
</ox-container>

<style>
  .ox-header, .ox-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .ox-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .ox-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .ox-container {
    margin-bottom: 40px;
  }
  
  .ox-container:nth-child(5) .ox-aside,
  .ox-container:nth-child(6) .ox-aside {
    line-height: 260px;
  }
  
  .ox-container:nth-child(7) .ox-aside {
    line-height: 320px;
  }
</style>
```
:::

### 实例

:::demo
```html
<ox-container style="height: 500px; border: 1px solid #eee">
  <ox-aside width="200px" style="background-color: rgb(238, 241, 246)">
    <ox-menu :default-openeds="['1', '3']">
      <ox-submenu index="1">
        <template slot="title"><i class="ox-icon-message"></i>导航一</template>
        <ox-menu-item-group>
          <template slot="title">分组一</template>
          <ox-menu-item index="1-1">选项1</ox-menu-item>
          <ox-menu-item index="1-2">选项2</ox-menu-item>
        </ox-menu-item-group>
        <ox-menu-item-group title="分组2">
          <ox-menu-item index="1-3">选项3</ox-menu-item>
        </ox-menu-item-group>
        <ox-submenu index="1-4">
          <template slot="title">选项4</template>
          <ox-menu-item index="1-4-1">选项4-1</ox-menu-item>
        </ox-submenu>
      </ox-submenu>
      <ox-submenu index="2">
        <template slot="title"><i class="ox-icon-menu"></i>导航二</template>
        <ox-menu-item-group>
          <template slot="title">分组一</template>
          <ox-menu-item index="2-1">选项1</ox-menu-item>
          <ox-menu-item index="2-2">选项2</ox-menu-item>
        </ox-menu-item-group>
        <ox-menu-item-group title="分组2">
          <ox-menu-item index="2-3">选项3</ox-menu-item>
        </ox-menu-item-group>
        <ox-submenu index="2-4">
          <template slot="title">选项4</template>
          <ox-menu-item index="2-4-1">选项4-1</ox-menu-item>
        </ox-submenu>
      </ox-submenu>
      <ox-submenu index="3">
        <template slot="title"><i class="ox-icon-setting"></i>导航三</template>
        <ox-menu-item-group>
          <template slot="title">分组一</template>
          <ox-menu-item index="3-1">选项1</ox-menu-item>
          <ox-menu-item index="3-2">选项2</ox-menu-item>
        </ox-menu-item-group>
        <ox-menu-item-group title="分组2">
          <ox-menu-item index="3-3">选项3</ox-menu-item>
        </ox-menu-item-group>
        <ox-submenu index="3-4">
          <template slot="title">选项4</template>
          <ox-menu-item index="3-4-1">选项4-1</ox-menu-item>
        </ox-submenu>
      </ox-submenu>
    </ox-menu>
  </ox-aside>
  
  <ox-container>
    <ox-header style="text-align: right; font-size: 12px">
      <ox-dropdown>
        <i class="ox-icon-setting" style="margin-right: 15px"></i>
        <ox-dropdown-menu slot="dropdown">
          <ox-dropdown-item>查看</ox-dropdown-item>
          <ox-dropdown-item>新增</ox-dropdown-item>
          <ox-dropdown-item>删除</ox-dropdown-item>
        </ox-dropdown-menu>
      </ox-dropdown>
      <span>王小虎</span>
    </ox-header>
    
    <ox-main>
      <ox-table :data="tableData">
        <ox-table-column prop="date" labox="日期" width="140">
        </ox-table-column>
        <ox-table-column prop="name" labox="姓名" width="120">
        </ox-table-column>
        <ox-table-column prop="address" labox="地址">
        </ox-table-column>
      </ox-table>
    </ox-main>
  </ox-container>
</ox-container>

<style>
  .ox-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  
  .ox-aside {
    color: #333;
  }
</style>

<script>
  export default {
    data() {
      const item = {
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      };
      return {
        tableData: Array(20).fill(item)
      }
    }
  };
</script>
```
:::

### Container Attributes
| 参数    | 说明     | 类型    | 可选值      | 默认值 |
|---------|----------|---------|-------------|--------|
| direction | 子元素的排列方向 | string | horizontal / vertical | 子元素中有 `ox-header` 或 `ox-footer` 时为 vertical，否则为 horizontal |

### Header Attributes
| 参数    | 说明     | 类型    | 可选值      | 默认值 |
|---------|----------|---------|-------------|--------|
| height | 顶栏高度 | string | — | 60px |

### Aside Attributes
| 参数    | 说明     | 类型    | 可选值      | 默认值 |
|---------|----------|---------|-------------|--------|
| width | 侧边栏宽度 | string | — | 300px |

### Footer Attributes
| 参数    | 说明     | 类型    | 可选值      | 默认值 |
|---------|----------|---------|-------------|--------|
| height | 底栏高度 | string | — | 60px |