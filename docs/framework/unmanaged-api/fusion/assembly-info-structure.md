---
title: "ASSEMBLY_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="3ee09-102">ASSEMBLY_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="3ee09-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="3ee09-103">包含有关在全局程序集缓存中注册程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="3ee09-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee09-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ee09-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3ee09-105">成员</span><span class="sxs-lookup"><span data-stu-id="3ee09-105">Members</span></span>  
  
|<span data-ttu-id="3ee09-106">成员</span><span class="sxs-lookup"><span data-stu-id="3ee09-106">Member</span></span>|<span data-ttu-id="3ee09-107">描述</span><span class="sxs-lookup"><span data-stu-id="3ee09-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="3ee09-108">以字节为单位，结构的大小。</span><span class="sxs-lookup"><span data-stu-id="3ee09-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="3ee09-109">此字段保留供将来扩展。</span><span class="sxs-lookup"><span data-stu-id="3ee09-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="3ee09-110">指示程序集有关的安装详细信息的标志。</span><span class="sxs-lookup"><span data-stu-id="3ee09-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="3ee09-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="3ee09-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="3ee09-112">-ASSEMBLYINFO_FLAG_INSTALLED 值，该值指示安装了程序集。</span><span class="sxs-lookup"><span data-stu-id="3ee09-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="3ee09-113">.NET Framework 的当前版本始终设置`dwAssemblyFlags`为此值。</span><span class="sxs-lookup"><span data-stu-id="3ee09-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="3ee09-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 值，该值指示程序集是常驻的负载。</span><span class="sxs-lookup"><span data-stu-id="3ee09-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="3ee09-115">.NET Framework 的当前版本永远不会设置`dwAssemblyFlags`为此值。</span><span class="sxs-lookup"><span data-stu-id="3ee09-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="3ee09-116">总的大小，以千字节为单位，该程序集包含的文件。</span><span class="sxs-lookup"><span data-stu-id="3ee09-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="3ee09-117">指向包含清单的文件的当前路径的字符串缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="3ee09-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="3ee09-118">该路径必须以 null 字符结尾。</span><span class="sxs-lookup"><span data-stu-id="3ee09-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="3ee09-119">宽字符，包括 null 终止符，数，`pszCurrentAssemblyPathBuf`包含。</span><span class="sxs-lookup"><span data-stu-id="3ee09-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ee09-120">要求</span><span class="sxs-lookup"><span data-stu-id="3ee09-120">Requirements</span></span>  
 <span data-ttu-id="3ee09-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ee09-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ee09-122">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3ee09-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3ee09-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ee09-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ee09-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ee09-124">See Also</span></span>  
 [<span data-ttu-id="3ee09-125">合成结构</span><span class="sxs-lookup"><span data-stu-id="3ee09-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="3ee09-126">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="3ee09-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)