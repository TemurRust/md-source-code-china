# File: tools/gopls/internal/lsp/protocol/tsprotocol.go

文件tsprotocol.go定义了与Typescript Language Server Protocol (LSP) 相关的结构体和常量。

该文件中的结构体（按照字母顺序）和作用如下：

1. AnnotatedTextEdit：带有注释的文本编辑结构。
2. ApplyWorkspaceEditParams：应用工作区编辑的参数。
3. ApplyWorkspaceEditResult：应用工作区编辑的结果。
4. BaseSymbolInformation：基本的符号信息结构。
5. CallHierarchyClientCapabilities：调用层次结构客户端能力。
6. CallHierarchyIncomingCall：调用层次结构的入向调用。
7. CallHierarchyIncomingCallsParams：调用层次结构的入向调用参数。
8. CallHierarchyItem：调用层次结构中的项。
9. CallHierarchyOptions：调用层次结构的选项。
10. CallHierarchyOutgoingCall：调用层次结构的出向调用。
11. CallHierarchyOutgoingCallsParams：调用层次结构的出向调用参数。
12. CallHierarchyPrepareParams：调用层次结构准备参数。
13. CallHierarchyRegistrationOptions：调用层次结构的注册选项。
14. CancelParams：取消请求的参数。
15. ChangeAnnotation：修改注释。
16. ChangeAnnotationIdentifier：修改注释的标识符。
17. ClientCapabilities：客户端能力。
18. CodeAction：代码操作。
19. CodeActionClientCapabilities：代码操作客户端能力。
20. CodeActionContext：代码操作上下文。
21. CodeActionKind：代码操作的种类/类型。
22. CodeActionOptions：代码操作选项。
23. CodeActionParams：代码操作参数。
24. CodeActionRegistrationOptions：代码操作的注册选项。
25. CodeActionTriggerKind：代码操作的触发方式。
26. CodeDescription：代码描述。
27. CodeLens：代码镜头。
28. CodeLensClientCapabilities：代码镜头客户端能力。
29. CodeLensOptions：代码镜头选项。
30. CodeLensParams：代码镜头参数。
31. CodeLensRegistrationOptions：代码镜头的注册选项。
32. CodeLensWorkspaceClientCapabilities：Workspace的代码镜头客户端能力。
33. Color：颜色。
34. ColorInformation：颜色信息。
35. ColorPresentation：颜色展示。
36. ColorPresentationParams：颜色展示参数。
37. Command：命令。
38. CompletionClientCapabilities：自动完成客户端能力。
39. CompletionContext：自动完成上下文。
40. CompletionItem：自动完成项。
41. CompletionItemKind：自动完成项的种类。
42. CompletionItemLabelDetails：自动完成项的标签详情。
43. CompletionItemTag：自动完成项的标签。
44. CompletionList：自动完成列表。
45. CompletionOptions：自动完成选项。
46. CompletionParams：自动完成参数。
47. CompletionRegistrationOptions：自动完成的注册选项。
48. CompletionTriggerKind：自动完成的触发方式。
49. ConfigurationItem：配置项。
50. ConfigurationParams：配置参数。
51. CreateFile：创建文件。
52. CreateFileOptions：创建文件的选项。
53. CreateFilesParams：创建文件的参数。
54. Declaration：声明。
55. DeclarationClientCapabilities：声明的客户端能力。
56. DeclarationLink：声明的链接。
57. DeclarationOptions：声明的选项。
58. DeclarationParams：声明的参数。
59. DeclarationRegistrationOptions：声明的注册选项。
60. Definition：定义。
61. DefinitionClientCapabilities：定义的客户端能力。
62. DefinitionLink：定义的链接。
63. DefinitionOptions：定义的选项。
64. DefinitionParams：定义的参数。
65. DefinitionRegistrationOptions：定义的注册选项。
66. DeleteFile：删除文件。
67. DeleteFileOptions：删除文件的选项。
68. DeleteFilesParams：删除文件的参数。
69. Diagnostic：诊断信息。
70. DiagnosticClientCapabilities：诊断信息的客户端能力。
71. DiagnosticOptions：诊断信息的选项。
72. DiagnosticRegistrationOptions：诊断信息的注册选项。
73. DiagnosticRelatedInformation：诊断信息的相关信息。
74. DiagnosticServerCancellationData：诊断信息的服务器取消数据。
75. DiagnosticSeverity：诊断信息的严重程度。
76. DiagnosticTag：诊断信息的标签。
77. DiagnosticWorkspaceClientCapabilities：Workspace的诊断信息能力。
78. DidChangeConfigurationClientCapabilities：配置变更的客户端能力。
79. DidChangeConfigurationParams：配置变更的参数。
80. DidChangeConfigurationRegistrationOptions：配置变更的注册选项。
81. DidChangeNotebookDocumentParams：Notebook文档变更的参数。
82. DidChangeTextDocumentParams：文本文档变更的参数。
83. DidChangeWatchedFilesClientCapabilities：文件监视的客户端能力。
84. DidChangeWatchedFilesParams：文件监视的参数。
85. DidChangeWatchedFilesRegistrationOptions：文件监视的注册选项。
86. DidChangeWorkspaceFoldersParams：Workspace文件夹变更的参数。
87. DidCloseNotebookDocumentParams：Notebook文档关闭的参数。
88. DidCloseTextDocumentParams：文本文档关闭的参数。
89. DidOpenNotebookDocumentParams：Notebook文档打开的参数。
90. DidOpenTextDocumentParams：文本文档打开的参数。
91. DidSaveNotebookDocumentParams：Notebook文档保存的参数。
92. DidSaveTextDocumentParams：文本文档保存的参数。
93. DocumentColorClientCapabilities：文档颜色的客户端能力。
94. DocumentColorOptions：文档颜色的选项。
95. DocumentColorParams：文档颜色的参数。
96. DocumentColorRegistrationOptions：文档颜色的注册选项。
97. DocumentDiagnosticParams：文档诊断的参数。
98. DocumentDiagnosticReport：文档诊断报告。
99. DocumentDiagnosticReportKind：文档诊断报告的种类。
100. DocumentDiagnosticReportPartialResult：文档诊断报告的部分结果。
101. DocumentFilter：文档过滤器。
102

