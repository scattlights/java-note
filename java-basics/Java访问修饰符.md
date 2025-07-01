| 修饰符   | 类内 | 同包 | 子类(不同包) | 其他包 |
|----------|-------|-------|--------------|--------|
| public   | √     | √     | √            | √      |
| protected| √     | √     | √            | ×      |
| default  | √     | √     | ×            | ×      |
| private  | √     | ×     | ×            | ×      |

---

> ⚠️ **Tips:** 在不同包的子类访问时，只能通过 `this` 或者子类对象本身访问 `protected` 成员，不能通过父类实例对象访问。

```java
public class Child extends Parent {
    public void test() {
        System.out.println(this.protectedVar);  // 可以
        Parent p = new Parent();
        System.out.println(p.protectedVar);     // 不可以，编译报错
    }
}
```
