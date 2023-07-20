# File: p2p/util.go

在go-ethereum项目中，p2p/util.go文件的作用是提供对等网络（peer-to-peer）的一些实用函数和数据结构。

expHeap结构体表示一个带有过期时间的堆的数据结构，用于存储和管理项（expItem结构体）。expItem结构体表示堆中的一个项，包含了项的值和过期时间。

- nextExpiry函数用于获取堆中下一个过期项的过期时间。
- add函数用于向堆中添加一个新的项，同时维护堆的顺序。
- contains函数用于检查堆中是否包含特定的项。
- expire函数用于从堆中删除所有已过期的项，并返回过期的项列表。
- Len函数用于获取堆的项的数量。
- Less函数用于比较两个项的过期时间。
- Swap函数用于交换堆中的两个项。
- Push函数用于向堆中添加一个新的项。
- Pop函数用于从堆中弹出并返回堆的最小项。

这些函数和数据结构的目的是提供一种高效的方式来管理和操作具有过期时间的项。堆的数据结构使得添加、移除和查找项的操作具有较低的时间复杂度。
