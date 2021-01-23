# Urho3D 源码学习

## C++ 知识点梳理

### inline（内联）函数
|  |  |
| :---- | :---- |
| 函数在 class body 内定义完成 | 自动成为 inline 候选人。 |
| 函数在 class body 外定义完成 | 需要在函数返回类型前面显示地加上 inline。 |

### virtual function（虚函数）
| 成员函数 | 描述 | 形式 | 备注 |
| :-----| :---- | :---- | :----|
| non-virtual 函数 | 你不希望派生类重新定义（override, 重写）它。 | `void function();` |  |
| virtual 函数 | 你希望派生类重新定义（override, 重写）它，且你对它已有默认定义。 | `virtual void function();` |  |
| pure virtual 函数 | 你希望派生类一定要重新定义（override, 重写）它，你对它没有默认定义。 | `virtual void function() = 0;` | 在声明语句的分号之前书写=0 |
