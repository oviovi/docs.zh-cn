---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074948"
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
注册的传入声明的声明身份验证管理器。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|指定派生的自定义类型<xref:System.Security.Claims.ClaimsAuthenticationManager>类。 详细了解如何指定`type`属性，请参阅 [自定义类型引用]。|  
  
### <a name="child-elements"></a>子元素  
 如果没有任何`type`属性，或者如果`type`属性引用<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不接受子元素; 但是，类派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>可以定义子配置元素。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 通过提供的默认行为<xref:System.Security.Claims.ClaimsAuthenticationManager>类将回显传入声明。 如果没有`type`指定属性或如果`type`特性指定<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不接受子元素。 您可以指定`type`属性来注册一个类型派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>类，以实现自定义行为。 派生的类可以支持的子元素通过配置`<claimsAuthenticationManager>`通过重写元素<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>方法来处理这些元素。 为子元素定义的架构由类的设计器。  
  
 `<claimsAuthenticationManager>`元素集<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>属性。  
  
## <a name="example"></a>示例  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
