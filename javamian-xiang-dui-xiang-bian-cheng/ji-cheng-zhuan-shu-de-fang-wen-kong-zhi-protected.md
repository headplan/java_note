# 继承专属的访问控制 : protected

Protected的可见性 = default\(缺省\) + 对子类可见 , 即使在不同的包里 . 

覆盖可以 , 但是不能让可见性更低 .

| 类内部 | 本包 | 子类 | 外部包 |
| :--- | :--- | :--- | :--- |
| private |  |  |  |
| default | default |  |  |
| protected | protected | protected |  |
| public | public | public | public |





