---
title: ISymUnmanagedWriter::DefineParameter 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6b01abc16334dbe091e7586efcce1c3e390a64e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426970"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>ISymUnmanagedWriter::DefineParameter 方法
在当前方法中定义的单个参数。 参数类型均从内方法的签名的参数的位置 （序列）。  
  
 如果参数在给定方法的元数据中定义的你不需要再次使用此方法定义。 在检查符号存储区前，符号读取器必须检查参数的正常元数据。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>参数  
 `name`  
 [in]参数名称。  
  
 `attributes`  
 [in]参数属性。  
  
 `sequence`  
 [in]参数签名中。  
  
 `addrKind`  
 [in]地址类型中。  
  
 `addr1`  
 [in]参数规格的第一个地址。  
  
 `addr2`  
 [in]参数规范第二个地址。  
  
 `addr3`  
 [in]参数规格的第三个地址。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
