# Instruction packet format

对于muti-word instruction 使用DISC 来指示 discontinuities. 那么对于16bit的指令怎么指示 discontinuities 呢？

## Glossary

预测：  
    静态预测  
        PFU如何知道一条跳转指令是taken还是notaken?  
    动态预测

```html
    调度：保证指令间不发生冒险，结构冒险，数据冒险（RAW，WAW，WAR）
        1.检测存不存在上述冒险
        2.根据之前的检测决定是否流出指令
    分支预测：取指令的时候不发生控制冒险
        1.等待条件满足后再取指令
        2.预测条件然后取指令
            2.1 预测条件
            2.2 得到跳转地址
        3.预测条件前瞻执行（执行在未确认前不改变处理器状态）
```

```html
    静态调度：取出的指令已经和在流水线中的指令不存在数据相关，或者虽然存在数据相关，但是通过bypass能够隐藏数据相关。不能隐藏的数据相关，在冲突硬件检测到的时候stall住流水线。
```

```html
    动态调度：使用专门的硬件对代码进行调度。
    动态调度的思想：
    1.指令流出，不存在结构冲突以及WAW冲突的情况下。
    2.与流水线中的指令在不存在RAW冲突的情况下发射。
    3.执行，在与流水线中的指令不存在WAR冲突的情况下，更新目的寄存器的值。
    
    如果后面的指令先于前面的指令完成，若发生异常，就会产生imprecise exception

    precise exception:

    imprecise exception:

``` 
