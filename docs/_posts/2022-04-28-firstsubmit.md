---
title: Fortran备忘录
---
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
 </script>

### 数值类型
各种数据类型的可取值范围或取值精度由kind值决定。

对于整型变量,其取值范围介于

$$
\left [-2^{8 * \mathrm{kind}-1}, 2^{8 * \mathrm{kind}-1} \right)
$$

示例:
```fortran
integer(kind=1) :: i1   ! [-128, 127],                                 E2
integer(kind=2) :: i2   ! [-32768, 32767],                             E4
integer(kind=4) :: i4   ! [-2147483648, 2147483647],                   E9
integer(kind=8) :: i8   ! [-9223372036854775808, 9223372036854775807], E18
```

对于整形数值，可以借助内置函数selected\_int\_kind(r)来获知满足对应数量级范围需求的最小kind数。

SELECTED\_INT\_KIND(r) : returns smallest kind of integer value with maximum range $10^{r}$

示例:
```fortran
integer, parameter :: scale = 4
integer(kind=selected_int_kind(scale)) :: xn ! xn in (-1.E4, 1.E4)
```

对于实型变量，其取值范围与精度由kind值决定。可以借助selected\_real\_kind(p,r)函数来获知满足相应取值范围与取值精度所需的最小kind数。

SELECTED\_REAL\_KIND(p,r) : return smallest kind of real value with a minimum of p decimal
digits of precision and maximum range $10^r$

```fortran
integer :: scale0 = 37
integer :: precision0 = 6
integer, parameter :: sgl = selected_real_kind(p=precision0,r=scale0)
real(sgl) :: x0 !

integer :: sacle1 = 200
integer :: precision1 = 15
integer, parameter :: dbl = selected_real_kind(p=precision1, r=scale1)
real(dbl) :: x1 !
```

