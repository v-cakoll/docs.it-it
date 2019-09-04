---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251751"
---
# <a name="trustedissuers"></a>\<> trustedIssuers
Configura l'elenco dei certificati dell'autorità emittente attendibile usati dal registro di sistema del nome dell'autorità emittente<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>basata sulla configurazione ().  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuerNameRegistry**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> trustedIssuers**  
  
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
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Aggiunge un certificato alla raccolta di autorità emittenti attendibili. Il certificato viene specificato con l' `thumbprint` attributo. Questo attributo è obbligatorio e deve contenere il formato con codifica ASN. 1 dell'identificazione personale del certificato. L' `name` attributo è facoltativo e può essere usato per specificare un nome descrittivo per il certificato.|  
|`<clear>`|Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.|  
|`<remove thumbprint=xs:string>`|Rimuove un certificato dalla raccolta di autorità emittenti attendibili. Il certificato viene specificato con l' `thumbprint` attributo. Questo attributo è obbligatorio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Configura il registro dei nomi delle autorità emittenti. **Importante:**  L' `type` attributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` dell'elemento deve fare riferimento alla classe affinché l'elemento sia valido. `<issuerNameRegistry>`|  
  
## <a name="remarks"></a>Note  
 Windows Identity Foundation (WIF) fornisce una singola implementazione della <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe. Il registro dei nomi delle autorità emittenti di configurazione mantiene un elenco di autorità emittenti attendibili caricate dalla configurazione. L'elenco associa ogni nome dell'autorità emittente al certificato X. 509 necessario per verificare la firma dei token prodotti dall'autorità emittente. L'elenco dei certificati dell'autorità emittente attendibile viene specificato `<trustedIssuers>` nell'elemento. Ogni elemento nell'elenco associa il nome di un emittente mnemonico al certificato X. 509 necessario per verificare la firma dei token prodotti dall'emittente. I certificati attendibili vengono specificati utilizzando il formato con codifica ASN. 1 dell'identificazione personale del certificato e vengono aggiunti alla raccolta `<add>` tramite l'elemento. È possibile cancellare o rimuovere autorità emittenti (certificati) dall'elenco usando gli `<clear>` elementi e. `<remove>`  
  
 L' `type` attributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` dell'elemento deve fare riferimento alla classe affinché l'elemento sia valido. `<issuerNameRegistry>`  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato come specificare il registro dei nomi delle autorità emittenti basato sulla configurazione.  
  
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
