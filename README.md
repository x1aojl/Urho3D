# Urho3D 源码学习

## C++ 知识点梳理

### inline（内联）函数
|  |  |
| :---- | :---- |
| 函数在 class body 内定义完成 | 自动成为 inline 候选人。 |
| 函数在 class body 外定义完成 | 需要在函数返回类型前面显示地加上 inline。 |

### virtual function（虚函数）
| non-virtual 函数 | virtual 函数 | pure virtual 函数 |
| :-----| :---- | :---- |
| 你不希望派生类重新定义（override, 重写）它。 | 你希望派生类重新定义（override, 重写）它，且你对它已有默认定义。 | 你希望派生类一定要重新定义（override, 重写）它，你对它没有默认定义。在声明语句的分号之前书写=0 |
| `void function();` | `virtual void function();` | `virtual void function() = 0;` |

### overload override overwrite
| overload 重载 | override 覆盖 | overwrite 重写 |
| :---- | :---- | :---- |
| 同一个类中, 函数名字相同但形参列表不同 | 派生类重写了基类的同名同参 virtual 函数 | 派生类重写了基类同名非 virtual 函数 |
