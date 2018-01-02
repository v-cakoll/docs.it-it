---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: cd981c8e48f003060c74787fdd2f29557c07901d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
Registra il resolver dei token di servizio che viene utilizzata dai gestori nella raccolta di gestori di token. Il resolver dei token di servizio viene utilizzato per risolvere il token di crittografia di token in arrivo e messaggi.  
  
 \<System. IdentityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<serviceTokenResolver >  
  
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
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Specifica il tipo di resolver del token di servizio. Entrambi i <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che deriva dalla <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe. Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato]. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza gestori di token.|  
  
## <a name="remarks"></a>Note  
 Per risolvere il token di crittografia di token in arrivo e messaggi, è possibile utilizzare il resolver dei token di servizio. Consente di recuperare la chiave che deve essere utilizzata per decrittografare i token in ingresso. È necessario specificare il `type` attributo. Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.  
  
 Alcuni gestori di token consentono di specificare le impostazioni di resolver del token del servizio nella configurazione. Le impostazioni ai gestori di token singoli sostituiscono quelle specificate nella raccolta di gestore del token di sicurezza.  
  
> [!NOTE]
>  Specifica il `<serviceTokenResolver>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti. Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
