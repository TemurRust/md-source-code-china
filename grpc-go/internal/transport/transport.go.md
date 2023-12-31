# File: grpc-go/internal/transport/transport.go

grpc-go/internal/transport/transport.go文件是gRPC-Go项目中的一个关键文件，主要实现了gRPC传输层的功能，包括与底层网络相关的代码和数据结构。

ErrConnClosing、errStreamDrain、errStreamDone和statusGoAway这几个变量的作用如下：
- ErrConnClosing表示连接正在关闭的错误。
- errStreamDrain表示流正在被处理的错误。
- errStreamDone表示流已经完成的错误。
- statusGoAway表示服务端已经关闭的标志。

bufferPool结构体是一个缓冲池，用于重用缓冲区，提高性能。
recvMsg结构体包含接收到的消息数据和元数据。
recvBuffer结构体表示接收缓冲区的状态和数据。
recvBufferReader是一个读取器，用于操作接收缓冲区。
streamState枚举表示流的不同状态。
Stream结构体表示gRPC的流，包含了流的各种信息和操作。
transportReader结构体用于从底层网络连接中读取数据。
transportState结构体表示底层传输层的状态和数据。
ServerConfig结构体包含了服务器的配置选项。
ConnectOptions结构体表示客户端连接选项。
Options结构体表示gRPC传输层的选项。
CallHdr结构体表示调用的头部信息。
ClientTransport接口定义了gRPC客户端传输的方法。
ServerTransport接口定义了gRPC服务器传输的方法。
ConnectionError是一个包含错误信息的结构体。
GoAwayReason枚举表示连接关闭的原因。
channelzData结构体用于存储gRPC通道的状态信息。

newBufferPool函数用于创建一个缓冲池。
get和put函数用于从缓冲池获取和释放缓冲区。
newRecvBuffer函数创建一个接收缓冲区。
load函数用于从接收缓冲区中读取数据。
Read函数用于从传输读取数据。
read函数尝试从接收缓冲区中读取完整的消息。
readClient函数从客户端连接中读取数据。
readAdditional函数用于读取附加消息数据。
isHeaderSent函数判断头部信息是否已发送。
updateHeaderSent函数用于更新头部已发送的状态。
swapState函数用于交换状态。
compareAndSwapState函数用于比较和交换状态。
getState函数用于获取当前状态。
waitOnHeader函数等待头部信息。
RecvCompress函数用于接收数据压缩。
SetSendCompress函数设置发送数据的压缩方式。
SendCompress函数用于发送数据压缩。
ClientAdvertisedCompressors函数获取客户端支持的压缩方式。
Done函数表示操作已完成。
Header函数获取调用的头部信息。
TrailersOnly函数表示只有尾部信息。
Trailer函数获取调用的尾部信息。
ContentSubtype函数获取内容子类型。
Context函数获取上下文信息。
Method函数获取方法名称。
Status函数获取状态码。
SetHeader函数设置头部信息。
SendHeader函数发送头部信息。
SetTrailer函数设置尾部信息。
write函数写入数据到传输。
BytesReceived函数获取接收的字节数。
Unprocessed函数获取未处理的字节数。
GoString函数返回Go语言的字符串表示形式。
NewClientTransport函数创建一个新的客户端传输。
connectionErrorf函数创建一个带有错误信息的连接错误。
Error函数返回错误信息。
Temporary函数判断错误是否是临时错误。
Origin函数返回错误的来源。
Unwrap函数返回原始错误。
ContextErr函数返回上下文错误。

