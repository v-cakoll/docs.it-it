---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252118"
---
# <a name="certificatevalidator"></a>\<certificateValidator>
Specifica un tipo personalizzato per la convalida del certificato. Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) è impostato su "Custom".  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> certificateValidation**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateValidator**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|type|Specifica un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe. Impostare l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) su "Custom" per usare questo tipo. Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md). facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.|  
  
## <a name="example"></a>Esempio  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
