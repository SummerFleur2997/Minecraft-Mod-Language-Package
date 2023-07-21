# 无线电模块

![原始的无线技术](item:tisadvanced:radio_module)

无线电模块相较红外模块而言具有更远的传输距离，不再局限于视距范围内。无线电模块传输的值将会被发送到*所有*距离在256米以内活动的无线电模块。

无线电模块从所有四个端口读取值，并将读取值作为其载荷传输。无线电模块将最后接收到的无线电数据包的值写入其所有四个端口。

无线电模块具有一个小型队列，用于保存最近接收到的数据包的值的列表。队列的长度由供应方指定。每当模块接收到一个数据包时，如果队列已满，则会忽略该数据包。数据包的值将按照接收的顺序依次写入无线电模块的端口。先发送的数据包会被优先接收，但同时发送的数据包可能以不定的顺序到达模块。

队列中的一个值只会被发送到一个端口，即值不会被复制；即使一个控制器周期内发生多次读取操作，最终也只会有一次操作成功。

此外，无线电模块在其正面的右上角有两个用于辅助调试的指示灯。当模块的内部缓存中存在需要被读取的数据包时，左侧的绿色指示灯会变为红色。当有数据包被发送时，右侧的蓝色指示灯会短时间闪烁。