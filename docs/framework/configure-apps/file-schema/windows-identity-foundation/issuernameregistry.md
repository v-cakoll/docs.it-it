---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: de3ceb5d84d17307c69e9155834a0a584e6920a1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185914"
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
Configura il registro dei nomi dell'autorità di certificazione che viene usato dai gestori nella raccolta di gestori di token.  
  
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
|tipo|Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe. Per altre informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti a tipi personalizzati].|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Quando la `type` attributo specifica il registro dei nomi basato sulla configurazione dell'autorità emittente (il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe), il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) elemento deve essere specificato. Il [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) elemento può accettare `<add>`, `<clear>`, o `<remove>` elementi come elementi figlio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza i gestori di token.|  
  
## <a name="remarks"></a>Note  
 Tutti i token dell'autorità di certificazione vengono convalidati tramite un registro dei nomi dell'autorità di certificazione. Si tratta di un oggetto da cui deriva il <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe. Il registro dei nomi dell'autorità di certificazione viene utilizzato per associare un nome mnemonico al materiale di crittografia che è necessario per verificare le firme dei token prodotti dall'autorità emittente corrispondente. Il registro dei nomi dell'autorità emittente mantiene un elenco di autorità di certificazione considerate attendibili dall'applicazione relying party (RP). Il tipo del Registro di sistema di nome dell'autorità di certificazione è specificato utilizzando il `type` attributo. Il `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato. Fornire la logica che elabora tali elementi figlio eseguendo l'override di <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> (metodo).  
  
 WIF fornisce una singola autorità di certificazione nome tipo del Registro di sistema per impostazione predefinita, il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe. Questa classe Usa un set di certificati di autorità emittenti attendibili che sono specificati nella configurazione. Richiede un elemento di configurazione figlio, `<trustedIssuers>`, in cui viene configurato l'insieme di certificati di autorità emittenti attendibili. Attendibili i certificati vengono specificati usando il ASN.1 formato dell'identificazione digitale del certificato con codifica e viene aggiunti o rimossi dalla raccolta utilizzando `<add>`, `<clear>`, o `<remove>` elementi.  
  
 Il `<issuerNameRegistry>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> classe.  
  
> [!NOTE]
>  Specifica la `<issuerNameRegistry>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti. Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come specificare l'autorità di certificazione di base di configurazione del registro dei nomi.  
  
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
