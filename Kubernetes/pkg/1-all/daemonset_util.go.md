# File: pkg/controller/daemon/util/daemonset_util.go

pkg/controller/daemon/util/daemonset_util.go文件是Kubernetes中的守护进程集控制器的工具类，包含了一些常用的守护进程集的功能函数实现。具体作用如下：

1. GetTemplateGeneration: 获取守护进程集的Pod模板的代数。

2. AddOrUpdateDaemonPodTolerations: 添加或者更新守护进程集中Pod的Tolerations。

3. CreatePodTemplate: 根据提供的参数创建守护进程集的Pod模板。

4. AllowsSurge: 判断当前守护进程集是否允许执行扩容操作。

5. SurgeCount: 计算当前守护进程集需要新增的Pod数量。

6. UnavailableCount: 计算当前守护进程集中失效的Pod数量。

7. IsPodUpdated: 判断守护进程集中指定的Pod是否需要更新。

8. ReplaceDaemonSetPodNodeNameNodeAffinity: 为守护进程集中的Pod设置节点亲和性规则。

9. GetTargetNodeName: 获取可以将Pod调度到的有效节点名称列表。

上述函数中，GetTemplateGeneration函数用于获取守护进程集中的Pod模板的代数，每次守护进程集更新都会使得Pod模板的代数增加。AddOrUpdateDaemonPodTolerations函数用于添加或更新守护进程集中的Pod的Tolerations，这些Tolerations指定了Pod可以在哪些节点上被调度。

CreatePodTemplate函数用于根据守护进程集的参数创建Pod模板，包括镜像名称、容器端口、挂载卷等。AllowsSurge函数用于判断守护进程集的当前状态是否可以执行扩容操作，如果当前状态不允许扩容操作，则返回false。

SurgeCount函数用于计算需要新增的Pod数量，它根据守护进程集的目标Pod数量 target、当前部署了多少个Pod current、以及已经失效的Pod数量 desiredUnavailable计算得到。

UnavailableCount函数用于计算当前守护进程集中失效的Pod数量，失效的Pod包括正在终止的Pod和已经被标记为终止的Pod。

IsPodUpdated函数用于判断指定的Pod是否需要进行更新，主要用于滚动升级时判断哪些Pod需要被更新。

ReplaceDaemonSetPodNodeNameNodeAffinity函数用于为守护进程集中的Pod设置节点亲和性规则，以调度Pod到指定的节点上。

GetTargetNodeName函数用于获取可以将Pod调度到的有效节点名称列表，其中包括所有符合守护进程集的节点选择器规则的节点。

