---
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- CondiitonalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ee3c3302d77bcc7b807c01ccb5bab172153ddda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459946"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a>ICorProfilerCallback5::ConditionalWeakTableElementReferences 方法
标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ConditionalWeakTableElementReferences(     [in]                     ULONG    cRootRefs,     [in, size_is(cRootRefs)] ObjectID keyRefIds[],     [in, size_is(cRootRefs)] ObjectID valueRefIds[],     [in, size_is(cRootRefs)] GCHandleID rootIds[]);};  
```  
  
#### <a name="parameters"></a>参数  
 `cRootRefs`  
 [in] `keyRefIds`、`valueRefIds` 和 `rootIds` 数组中的元素数。  
  
 `keyRefIds`  
 [in] 一个包含对象 ID 的数组，其中每个对象 ID 都包含相关句柄对中主要元素的 `ObjectID`。  
  
 `valueRefIds`  
 [in] 一个包含对象 ID 的数组，其中每个对象 ID 都包含相关句柄对中次要元素的 `ObjectID`。 (`keyRefIds[i]`保留`valueRefIds[i]`处于活动状态。)  
  
 `rootIds`  
 [in] 一个包含 `GCHandleID` 值的数组，这些值指向包含有关垃圾回收根的附加信息的整数。  
  
 在该回调本身中，由 `ObjectID` 方法返回的任何 `ConditionalWeakTableElementReferences` 值都无效，因为垃圾回收器可能正处于将对象从旧位置移到新位置的过程中。 因此，探查器不应在 `ConditionalWeakTableElementReferences` 调用期间尝试检查对象。 在 `GarbageCollectionFinished` 时，已经将所有对象都移动到其新位置，并且检查可能已完成。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何实现[ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)以及使用此方法。  
  
```  
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(  
    ULONG      cRootRefs,  
    ObjectID   keyRefIds[],  
    ObjectID   valueRefIds[],  
    GCHandleID rootIds[])  
{  
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");  
    for (unsigned int i = 0; i < cRootRefs; ++i)  
    {  
        // Save dependency to XML for later retrieval  
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or store dependency to an internal map  
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or add arc to object graph  
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);  
    }  
    return S_OK;  
}  
```  
  
## <a name="remarks"></a>备注  
 探查器以[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]或更高版本实现[ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)接口并记录由指定的依赖关系`ConditionalWeakTableElementReferences`方法。 `ICorProfilerCallback5` 提供所表示的活动对象之间的依赖项的完整集`ConditionalWeakTable`条目。 这些依赖关系和成员字段引用指定[icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)方法启用托管的探查器以生成活动对象的完整对象图。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback5 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)
