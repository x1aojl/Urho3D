# Urho3D 源码学习

## C++ 知识点梳理

### 访问控制
#### class / struct 里成员的默认访问控制
定义在第一个访问说明符之前的成员：class 中默认为 private，struct 中默认为 public。
| <sub>类型</sub> \ <sup>成员访问说明符</sup> | public | protected | private |
| :---- | :----: | :----: | :----: |
| 类的实例 | yes  | no | no |
| 类的友元 | yes | yes | yes |
| 类的派生类 | yes | yes | no |

#### class / struct 继承链里的默认访问控制
如果不写继承方式：class 默认以 private 的方式继承，struct 默认以 public 的方式继承。
| <sub>继承方式</sub> \ <sup>基类成员</sup> | public | protected | private |
| :---- | :---- | :---- | :---- |
| public | public  | protected | 不可访问 |
| protected | protected | protected | 不可访问 |
| private | private | private | 不可访问 |

### inline（内联）函数
| | |
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
