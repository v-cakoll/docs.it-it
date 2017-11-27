---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 33ef3ca88462595d81d269a92a643b43c9aea025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttrustedissuersgt"></a>&lt;trustedIssuers&gt;
Consente di configurare l'elenco di certificati di autorità emittenti attendibili utilizzati dal Registro di sistema di nome dell'autorità di certificazione basata sulla configurazione (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<System. IdentityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
\<trustedIssuers >  
  
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
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Aggiunge un certificato per la raccolta di autorità emittenti attendibili. Il certificato è specificato con il `thumbprint` attributo. Questo attributo è obbligatorio e deve contenere il modulo ASN. 1 codificata dell'identificazione digitale del certificato. Il `name` attributo è facoltativo e può essere utilizzato per specificare un nome descrittivo per il certificato.|  
|`<clear>`|Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.|  
|`<remove thumbprint=xs:string>`|Rimuove un certificato dalla raccolta di autorità emittenti attendibili. Il certificato è specificato con il `thumbprint` attributo. Questo attributo è obbligatorio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Consente di configurare il Registro di sistema di nome dell'autorità di certificazione. **Importante:** il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento di <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.|  
  
## <a name="remarks"></a>Note  
 Windows Identity Foundation (WIF) fornisce un'implementazione singola del <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe. Il Registro di sistema di configurazione dell'autorità di certificazione nome gestisce un elenco di autorità emittenti attendibili che viene caricato dalla configurazione. Nell'elenco, ciascun nome dell'autorità emittente associato il certificato x. 509 che è necessaria per verificare la firma dei prodotti dall'emittente del token. L'elenco di certificati di autorità emittenti attendibili viene specificato sotto il `<trustedIssuers>` elemento. Ogni elemento nell'elenco associa un nome di tasto di scelta dell'autorità emittente con il certificato x. 509 che è necessario verificare la firma di token generato da tale autorità emittente. Certificati trusted vengono specificati utilizzando l'ASN. 1 formato dell'identificazione digitale del certificato con codifica e vengono aggiunti insieme utilizzando `<add>` elemento. È possibile cancellare o rimuovere gli emittenti (certificati) dall'elenco utilizzando il `<clear>` e `<remove>` elementi.  
  
 Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento di <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come specificare l'autorità emittente di base di configurazione del Registro di sistema di nome.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
