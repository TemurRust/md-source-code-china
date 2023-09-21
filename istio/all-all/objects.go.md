# File: istio/operator/pkg/object/objects.go

在istio项目中，istio/operator/pkg/object/objects.go文件的作用是定义了一些用于处理Kubernetes对象的工具函数和结构体。

- K8sObject结构体是一个通用的Kubernetes对象表示，包括了对象的API版本（APIVersion）、种类（Kind）、元数据（Metadata）和规范（Spec）等字段。
- K8sObjects结构体是K8sObject的切片，用于表示一组Kubernetes对象。
- NewK8sObject是一个用于创建K8sObject的工具函数，根据给定的API版本、种类和名称创建一个新的K8sObject对象。
- Hash函数用于计算Kubernetes对象的哈希值，用于唯一标识对象。
- FromHash函数用于从哈希值中解析出Kubernetes对象的API版本、种类和名称。
- HashNameKind函数用于计算Kubernetes对象的名称和种类的组合哈希值。
- ParseJSONToK8sObject和ParseYAMLToK8sObject函数用于将JSON和YAML格式的数据解析为K8sObject对象。
- UnstructuredObject函数用于将未结构化的数据转化为Kubernetes对象。
- ResolveK8sConflict函数用于解决Kubernetes对象之间的冲突，保留较新的对象。
- Unstructured函数用于将Kubernetes对象转化为未结构化的数据。
- Container、GroupVersionKind、Version、JSON、YAML、YAMLDebugString、String、Keys等函数用于方便地操作Kubernetes对象的各个字段和属性。
- UnstructuredItems函数用于提取未结构化的数据列表。
- ParseK8sObjectsFromYAMLManifest函数用于从YAML格式的清单文件中解析出Kubernetes对象列表。
- ParseK8sObjectsFromYAMLManifestFailOption函数用于控制解析YAML清单文件的失败行为。
- YAMLManifest函数用于将Kubernetes对象列表转化为YAML格式的清单文件。
- Sort函数用于按照一定的规则对Kubernetes对象进行排序。
- ToMap和ToNameKindMap函数用于将Kubernetes对象列表转化为字典形式的数据。
- Valid函数用于判断Kubernetes对象是否有效。
- FullName函数用于获取Kubernetes对象的完整名称。
- Equal函数用于判断两个Kubernetes对象是否相等。
- istioCustomResources函数用于获取Istio自定义资源的列表。
- DefaultObjectOrder函数用于设置Kubernetes对象的默认排序规则。
- ObjectsNotInLists函数用于获取两个Kubernetes对象列表中不同的对象。
- KindObjects函数用于根据Kubernetes对象的种类将其分类。
- ParseK8SYAMLToIstioOperator函数用于将Kubernetes对象解析为Istio Operator中的对象。
- AllObjectHashes函数用于获取所有Kubernetes对象的哈希值。
- resolvePDBConflict函数用于解决Pod Disruption Budget（PDB）对象之间的冲突。
- isValidKubernetesObject函数用于判断是否为有效的Kubernetes对象。
