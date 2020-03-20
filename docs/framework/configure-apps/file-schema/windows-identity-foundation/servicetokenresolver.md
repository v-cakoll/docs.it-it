---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152580"
---
# <a name="servicetokenresolver"></a>\<> serviceTokenResolver
Registra il resolver di token del servizio utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token del servizio viene utilizzato per risolvere il token di crittografia nei token e nei messaggi in ingresso.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|type|Specifica il tipo di resolver del token del servizio. Il <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che <xref:System.IdentityModel.Selectors.SecurityTokenResolver> deriva dalla classe. Per ulteriori informazioni su `type` come specificare l'attributo, vedere [Riferimenti ai tipi personalizzati]. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>securityTokenHandlerConfiguration](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Osservazioni  
 Il resolver del token del servizio può essere utilizzato per risolvere il token di crittografia nei token e nei messaggi in ingresso. Viene utilizzato per recuperare la chiave che deve essere utilizzata per decrittografare i token in ingresso. È necessario `type` specificare l'attributo. Il tipo specificato <xref:System.IdentityModel.Selectors.SecurityTokenResolver> può essere o un tipo <xref:System.IdentityModel.Selectors.SecurityTokenResolver> personalizzato che deriva dalla classe .  
  
 Alcuni gestori di token consentono di specificare le impostazioni del resolver del token del servizio nella configurazione. Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.  
  
> [!NOTE]
> Specificare `<serviceTokenResolver>` l'elemento come elemento figlio dell'elemento [ \<identityConfiguration>](identityconfiguration.md) è deprecato, ma è comunque supportato per la compatibilità con le versioni precedenti. Le impostazioni `<securityTokenHandlerConfiguration>` dell'elemento `<identityConfiguration>` sostituiscono quelle dell'elemento.  
  
## <a name="example"></a>Esempio  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
