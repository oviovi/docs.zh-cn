---
title: '&lt;transportConfigurationType&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 5d13ef51444e1600b0cea5d55a1b5e332e440bc6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749629"
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a>&lt;transportConfigurationType&gt; 的 &lt;add&gt;
此元素是一个键/值对，可标识特定传输的类型。  
  
 \<system.ServiceModel>  
\<ServiceHostingEnvironment >  
\<transportConfigurationTypes >  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|必需的字符串属性。<br /><br /> 包含一个唯一标识传输类型的用户定义的键。|  
|transportConfigurationType|一个包含实现特定传输的类型的字符串。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<transportConfigurationTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|一个实现特定传输的类型的集合。|  
  
## <a name="example"></a>示例  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [承载](../../../../../docs/framework/wcf/feature-details/hosting.md)
