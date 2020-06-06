---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251959"
---
# \<issuerNameRegistry>
Configura il registro di sistema dei nomi delle autorità emittenti utilizzato dai gestori nella raccolta di gestori di token.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
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
|type|Tipo che deriva dalla <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe. Per ulteriori informazioni su come specificare un oggetto personalizzato `type` , vedere [riferimenti ai tipi personalizzati].|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|Quando l' `type` attributo specifica il registro dei nomi delle autorità emittenti basato sulla configurazione (la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe), [\<trustedIssuers>](trustedissuers.md) è necessario specificare l'elemento. L' [\<trustedIssuers>](trustedissuers.md) elemento può assumere `<add>` `<clear>` elementi, o `<remove>` come elementi figlio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Commenti  
 Tutti i token dell'autorità emittente vengono convalidati utilizzando un registro di sistema del nome dell'autorità emittente. Si tratta di un oggetto che deriva dalla <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe. Il registro dei nomi delle autorità emittenti viene utilizzato per associare un nome mnemonico al materiale crittografico necessario per verificare le firme dei token prodotti dall'emittente corrispondente. Il registro dei nomi delle autorità emittenti gestisce un elenco di autorità di certificazione ritenute attendibili dall'applicazione relying party (RP). Il tipo del registro dei nomi delle autorità emittenti viene specificato mediante l' `type` attributo. L' `<issuerNameRegistry>` elemento può avere uno o più elementi figlio che forniscono la configurazione per il tipo specificato. Si fornisce la logica che elabora questi elementi figlio eseguendo l'override del <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> metodo.  
  
 WIF fornisce un singolo tipo di registro dei nomi delle autorità emittenti, ovvero la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe. Questa classe usa un set di certificati Autorità di certificazione attendibili specificati nella configurazione. Richiede un elemento di configurazione figlio, `<trustedIssuers>` , in cui è configurata la raccolta di certificati dell'autorità emittente attendibile. I certificati attendibili vengono specificati utilizzando il formato con codifica ASN. 1 dell'identificazione personale del certificato e vengono aggiunti o rimossi dalla raccolta tramite `<add>` `<clear>` `<remove>` gli elementi, o.  
  
 L' `<issuerNameRegistry>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> classe.  
  
> [!NOTE]
> Specificare l' `<issuerNameRegistry>` elemento come elemento figlio dell' [\<identityConfiguration>](identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti. Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override di quelle nell' `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato come specificare il registro dei nomi delle autorità emittenti basato sulla configurazione.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
