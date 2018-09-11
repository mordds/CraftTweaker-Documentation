# Zen 操作符

[`@ZenOperator`](/Dev_Area/ZenAnnotations/Annotation_ZenOperator/) 注解

| ZenOperator  | 关联的符号                  | 其他关联符号 / 说明                                                |
| ------------ | --------------------------- | ------------------------------------------------------------------ |
| ADD          | `+`                         | `+=`                                                               |
| SUB          | `-`                         | `-=`                                                               |
| MUL          | `*`                         | `*=`                                                               |
| DIV          | `/`                         | `/=`                                                               |
| MOD          | `%`                         | `%=`                                                               |
| CAT          | `~`                         | `~=`                                                               |
| OR           | `|`                         | `|=`                                                               |
| AND          | `&`                         | `&=`                                                               |
| XOR          | `^`                         | `^=`                                                               |
| NEG          | `-`                         |                                                                    |
| NOT          | `!`                         |                                                                    |
| INDEXSET     | `[i] = v`                   |                                                                    |
| INDEXGET     | `[i]`                       |                                                                    |
| RANGE        | `i .. v`                    | `i to v`                                                           |
| CONTAINS     | `in`                        | `has`                                                              |
| COMPARE      | `==` `<` `>` `<=` `>=` `!=` | 注解的函数应该返回一个像 `Integer.compare` 一样的 int 值           |
| MEMBERGETTER | `.member`                   | 和 [`@ZenMemberSetter`](/Dev_Area/ZenAnnotations/ZenMembers/) 一样 |
| MEMBERSETTER | `.member = v`               |                                                                    |
| EQUALS       | `=`                         |                                                                    |
