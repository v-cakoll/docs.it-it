---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48031931"
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
Registra il resolver dei token di servizio che viene usato dai gestori nella raccolta di gestori di token. Il resolver dei token di servizio viene usato per risolvere il token di crittografia token in arrivo e messaggi.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
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
|tipo|Specifica il tipo di resolver di token del servizio. Entrambi i <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che deriva dal <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe. Per altre informazioni su come specificare il `type` attributo, vedere [riferimenti a tipi personalizzati]. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza i gestori di token.|  
  
## <a name="remarks"></a>Note  
 Il resolver dei token di servizio è utilizzabile per risolvere il token di crittografia token in arrivo e messaggi. Utilizzato per recuperare la chiave da usare per decrittografare i token in ingresso. È necessario specificare il `type` attributo. Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva dal <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.  
  
 Alcuni gestori di token consentono di specificare le impostazioni di resolver dei token del servizio nella configurazione. Le impostazioni ai singoli gestori di token sostituiscono quelle specificate nella raccolta di gestori di token di sicurezza.  
  
> [!NOTE]
>  Specifica la `<serviceTokenResolver>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti. Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
