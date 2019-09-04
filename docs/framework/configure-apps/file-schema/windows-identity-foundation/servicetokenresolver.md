---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251841"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token. Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceTokenResolver**  
  
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
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|type|Specifica il tipo del resolver del token del servizio. Tipo o un tipo che deriva <xref:System.IdentityModel.Selectors.SecurityTokenResolver> dalla classe. <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati]. Richiesto.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 Il resolver del token del servizio può essere usato per risolvere il token di crittografia sui token e i messaggi in ingresso. Viene usato per recuperare la chiave che deve essere usata per decrittografare i token in ingresso. È necessario specificare l' `type` attributo. Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva <xref:System.IdentityModel.Selectors.SecurityTokenResolver> dalla classe.  
  
 Alcuni gestori di token consentono di specificare le impostazioni del resolver del token del servizio nella configurazione. Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.  
  
> [!NOTE]
> Specificare l' `<serviceTokenResolver>` elemento come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti. Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.  
  
## <a name="example"></a>Esempio  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 