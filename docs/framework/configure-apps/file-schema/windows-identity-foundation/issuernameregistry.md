---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
Consente di configurare il Registro di sistema nome dell'autorità di certificazione che viene utilizzata dai gestori nella raccolta di gestori di token.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
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
|tipo|Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe. Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti al tipo personalizzato].|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Quando il `type` attributo specifica il Registro di sistema di nome dell'autorità di certificazione basata sulla configurazione (il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe), il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) elemento deve essere specificato. Il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) può richiedere l'elemento `<add>`, `<clear>`, o `<remove>` elementi come elementi figlio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza gestori di token.|  
  
## <a name="remarks"></a>Note  
 Tutti i token dell'autorità di certificazione vengono convalidati mediante un registro di sistema di nome dell'autorità di certificazione. Si tratta di un oggetto da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe. Il Registro di sistema di nome dell'autorità di certificazione viene utilizzato per associare un nome di tasti di scelta rapida per il materiale di crittografia è necessaria per verificare le firme di token generato dall'emittente corrispondente. Il Registro di sistema di nome dell'autorità emittente mantiene un elenco delle autorità emittenti attendibili per l'applicazione relying party (RP). Il tipo del Registro di sistema di nome dell'autorità di certificazione è specificato utilizzando il `type` attributo. Il `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato. Fornire la logica che elabora gli elementi figlio, eseguendo l'override di <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> metodo.  
  
 WIF offre una singola autorità di certificazione come nome del Registro di sistema predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe. Questa classe Usa un set di autorità emittenti attendibili i certificati che sono specificati nella configurazione. Richiede un elemento di configurazione figlio, `<trustedIssuers>`, in cui viene configurato l'insieme dei certificati dell'autorità emittente attendibile. Attendibili i certificati vengono specificati utilizzando l'ASN. 1 formato dell'identificazione digitale del certificato con codifica e viene aggiunti o rimossi dalla raccolta utilizzando `<add>`, `<clear>`, o `<remove>` elementi.  
  
 Il `<issuerNameRegistry>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> classe.  
  
> [!NOTE]
>  Specifica il `<issuerNameRegistry>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti. Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come specificare l'autorità emittente di base di configurazione del Registro di sistema di nome.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
