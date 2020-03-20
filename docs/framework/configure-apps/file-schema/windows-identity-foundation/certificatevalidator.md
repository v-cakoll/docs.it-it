---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152788"
---
# <a name="certificatevalidator"></a>\<> certificateValidator
Specifica un tipo personalizzato per la convalida del certificato. Questo tipo viene utilizzato `certificateValidationMode` solo se l'attributo dell'elemento [ \<certificateValidation>](certificatevalidation.md) è impostato su "Custom".  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateConvalida>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>certificateValidator**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|type|Specifica un tipo personalizzato che <xref:System.IdentityModel.Selectors.X509CertificateValidator> deriva dalla classe. Impostare `certificateValidationMode` l'attributo dell'elemento [ \<certificateValidation>](certificatevalidation.md) su "Custom" per utilizzare questo tipo. Per ulteriori informazioni su `type` come specificare l'attributo, vedere Riferimenti ai tipi [personalizzati](../windows-workflow-foundation/index.md). Facoltativa.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<certificateConvalida>](certificatevalidation.md)|Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.|  
  
## <a name="example"></a>Esempio  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
