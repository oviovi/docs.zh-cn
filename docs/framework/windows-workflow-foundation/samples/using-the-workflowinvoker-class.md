---
title: 使用 WorkflowInvoker 类
ms.date: 03/30/2017
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
ms.openlocfilehash: d6525dbbd30aae95be4c4ee1de267736e557a541
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748697"
---
# <a name="using-the-workflowinvoker-class"></a>使用 WorkflowInvoker 类
此示例演示如何使用 <xref:System.Activities.WorkflowInvoker> 类将活动作为方法进行调用。  
  
## <a name="sample-details"></a>示例详细信息  
 执行活动的最简单方式是使用 <xref:System.Activities.WorkflowInvoker> 类。 该类是为直接将活动作为方法调用运行而设计的。 它是一种性能极佳且易于使用的轻量 API，当执行活动不需要其他宿主变体提供的控件基础结构时使用此 API。  
  
 此示例使用派生的自定义活动<xref:System.Activities.CodeActivity%601>< Int32\>名为`Add`后者添加两个<xref:System.Activities.InArgument%601>，`X`并`Y`，并返回`Result` <xref:System.Activities.OutArgument%601>。 (<xref:System.Activities.CodeActivity%601>\<T > 派生<xref:System.Activities.Activity%601>< T\>，其中包含<xref:System.Activities.OutArgument%601> \<T > 名为`Result`。)一个`Dictionary`\<字符串、 对象 > 用于将参数传递到通过调用的活动<xref:System.Activities.WorkflowInvoker>。 字典的键与调用的活动上的自变量名相对应。 与特定键关联的值将绑定到键所标识的参数。  
  
 此示例调用 <xref:System.Activities.WorkflowInvoker.Invoke%2A> 并传递一个字典，其中包含 `X` 和 `Y` 的值。 <xref:System.Activities.WorkflowInvoker> 类将这些值绑定到 `Add` 活动的参数，执行活动并返回结果。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 Invoker.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`