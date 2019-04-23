---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221704"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
Consente di configurare l'elenco dei certificati dell'autorità emittente attendibile usato per il registro dei nomi basato sulla configurazione dell'autorità di certificazione (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
\<trustedIssuers>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Aggiunge un certificato per la raccolta di autorità emittenti attendibili. Il certificato è specificato con il `thumbprint` attributo. Questo attributo è obbligatorio e deve contenere il form codificato ASN.1 dell'identificazione digitale del certificato. Il `name` attributo è facoltativo e può essere utilizzato per specificare un nome descrittivo per il certificato.|  
|`<clear>`|Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.|  
|`<remove thumbprint=xs:string>`|Rimuove un certificato dalla raccolta di autorità emittenti attendibili. Il certificato è specificato con il `thumbprint` attributo. Questo attributo è obbligatorio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Configura il registro dei nomi dell'autorità di certificazione. **Importante:**  Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento le <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.|  
  
## <a name="remarks"></a>Note  
 Windows Identity Foundation (WIF) fornisce un'implementazione singola del <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe per impostazione predefinita, il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe. Il Registro di sistema configurazione nome dell'autorità emittente mantiene un elenco di autorità emittenti attendibili che viene caricato dalla configurazione. L'elenco associa ogni nome dell'autorità emittente con il certificato X.509 che è necessario per verificare la firma dei token prodotti dall'autorità di certificazione. L'elenco dei certificati di autorità emittenti attendibili viene specificato sotto il `<trustedIssuers>` elemento. Ogni elemento nell'elenco associa un nome dell'autorità di certificazione tasti di scelta rapida con il certificato X.509 che è necessario per verificare la firma dei token prodotti dall'autorità emittente in questione. Attendibili i certificati vengono specificati usando il ASN.1 formato dell'identificazione digitale del certificato con codifica e vengono aggiunti insieme tramite `<add>` elemento. È possibile cancellare o rimuovere autorità emittenti (certificati) dall'elenco utilizzando il `<clear>` e `<remove>` elementi.  
  
 Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento le <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come specificare l'autorità di certificazione di base di configurazione del registro dei nomi.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
