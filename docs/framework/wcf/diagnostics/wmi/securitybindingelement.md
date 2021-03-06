---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: 19c65b3028ad63b8a78205d00f44cc32322648d5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47069969"
---
# <a name="securitybindingelement"></a>SecurityBindingElement
SecurityBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>方法  
 SecurityBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 SecurityBindingElement 类具有下列属性：  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  
 数据类型：String  
  
 访问类型：只读  
  
 指定要用于绑定的算法。  
  
### <a name="includetimestamp"></a>IncludeTimestamp  
 数据类型：Boolean  
  
 访问类型：只读  
  
 一个布尔值，指定是否每个消息都包含时间戳。  
  
### <a name="keyentropymode"></a>KeyEntropyMode  
 数据类型：String  
  
 访问类型：只读  
  
 用于创建密钥的熵的来源。  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  
 数据类型：LocalServiceSecuritySettings  
  
 访问类型：只读  
  
 本地服务的特定于绑定的安全属性。  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  
 数据类型：String  
  
 访问类型：只读  
  
 消息安全使用的版本。  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  
 数据类型：String  
  
 访问类型：只读  
  
 此绑定的安全标头中的元素顺序。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
