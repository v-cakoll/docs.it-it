---
title: Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5
ms.date: 03/30/2017
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
author: BrucePerlerMS
ms.openlocfilehash: ef5801ccfdda22b1c89c22ea9c2b14ea0855ed26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670033"
---
# <a name="namespace-mapping-between-wif-35-and-wif-45"></a>Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5

A partire da .NET 4.5, Windows Identity Foundation (WIF) è stato completamente integrato in .NET Framework. Questa integrazione ha comportato modifiche dei nomi e alcuni consolidamenti degli spazi dei nomi WIF e della superficie dell'API. In questo argomento sono disponibili indicazioni e un mapping generale tra gli spazi dei nomi WIF 3.5 e gli spazi dei nomi WIF 4.5. Le informazioni non sono da considerarsi esaustive, ma lo scopo è piuttosto quello di offrire indicazioni generali su dove trovare classi note di WIF 3.5 in WIF 4.5. Per altre informazioni dettagliate sulle differenze tra WIF 3.5 e WIF 4.5, vedere [Novità di Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md). Per istruzioni su come eseguire la migrazione di applicazioni compilate con WIF 3.5 a WIF 4.5, vedere [Linee guida per la migrazione di un'applicazione compilata con le versioni di WIF dalla 3.5 alla 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).

## <a name="wif-35-to-wif-45-namespace-map"></a>Mapping degli spazi dei nomi WIF 3.5 e WIF 4.5

Le classi WIF, raccolte negli spazi dei nomi `Microsoft.IdentityModel` in WIF 3.5, sono ora distribuite tra gli spazi dei nomi `System.Security.Claims`, `System.ServiceModel.Security` e `System.IdentityModel` in WIF 4.5. Inoltre, alcuni spazi dei nomi WIF 3.5 sono stati consolidati o eliminati interamente in WIF 4.5.

> [!IMPORTANT]
> Questi spazi dei nomi `System.IdentityModel` contengono classi che implementano il modello di identità basato sulle attestazioni di WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> e <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. Il modello di identità basato sulle attestazioni di WCF è stato sostituito da WIF. Non usare le classi in questi tre spazi dei nomi per la compilazione di soluzioni basate su WIF.

La tabella seguente include informazioni su dove è possibile trovare le classi WIF 3.5 in WIF 4.5.

|**Spazio dei nomi WIF 3.5**|**Spazio dei nomi WIF 4.5**|**Commenti**|
|-|-|-|
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=nameWithType>|- La maggior parte delle classi che rappresentano costanti non è implementata.<br />- Le classi usate per creare servizi token di sicurezza sono state spostate da `Microsoft.IdentityModel.SecurityTokenService` a <xref:System.IdentityModel?displayProperty=nameWithType>.<br />- Le classi in `Microsoft.IdentityModel.Threading` sono state spostate in <xref:System.IdentityModel?displayProperty=nameWithType>.<br />- Le classi `ExceptionMapper` e `MruSecurityTokenCache` non sono implementate.|
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=nameWithType>|- Le interfacce `IClaimsPrincipal` e `IClaimsIdentity` non sono implementate in WIF 4.5. Invece, <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType> e <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> sono ora le classi di base da cui deriva la maggior parte delle classi per entità di sicurezza e identità .NET. Questo significa che non servono classi specialistiche per identità ed entità di sicurezza delle attestazioni come `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` e `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` in WIF 4.5 ed è possibile usare <xref:System.Security.Principal.WindowsPrincipal?displayProperty=nameWithType> e <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType>. Lo stesso vale per le altre classi specialistiche per identità e entità di sicurezza delle attestazioni esistenti in WIF 3.5.<br />- La classe `Microsoft.IdentityModel.Claims.ClaimsCollection` non è implementata in WIF 4.5. Le raccolte di attestazioni vengono invece esposte come raccolte enumerabili di tipo <xref:System.Security.Claims.Claim?displayProperty=nameWithType>.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType> e <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> forniscono metodi che ora supportano LINQ.|
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=nameWithType>|Alcuni elementi e classi hanno subito modifiche di nome e alcuni sono stati eliminati in WIF 4.5. Ad esempio, `Microsoft.IdentityModel.Configuration.ServiceConfiguration` ora è <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=nameWithType>.|
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Protocols.WSIdentity`|Non implementato in WIF 4.5|WIF 3.5 conteneva classi per il supporto di CardSpace, non implementate in WIF 4.5.|
|`Microsoft.IdentityModel.Protocols.WSTrust`|Suddivisi tra gli spazi dei nomi <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType> e <xref:System.ServiceModel.Security?displayProperty=nameWithType>.|Le classi che rappresentano elementi WS-Trust sono nello spazio dei nomi <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>. Ad esempio, la classe <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>. Le classi che rappresentano i contratti di servizio WCF, gli host del servizio e i canali che consentono a un servizio WCF di comunicare mediante il protocollo WS-Trust si trovano nello spazio dei nomi <xref:System.ServiceModel.Security?displayProperty=nameWithType>. Ad esempio, la classe <xref:System.ServiceModel.Security.WSTrustServiceHost>.|
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|Non implementato in WIF 4.5|-|
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|Non implementato in WIF 4.5|Classi contenute che rappresentano costanti di crittografia XML in WIF 3.5. Queste costanti non sono implementate in WIF 4.5.|
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=nameWithType>|La classe `EnvelopingSignature` e le classi che rappresentano costanti non sono implementate.|
|`Microsoft.IdentityModel.SecurityTokenService`|Suddivisi tra gli spazi dei nomi <xref:System.IdentityModel?displayProperty=nameWithType>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType> e <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>.|-|
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>|Le classi che forniscono la configurazione per gli scenari passivi (WS-Federation) sono state spostate in gran parte in <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>. Alcune di queste classi sono tuttavia in <xref:System.IdentityModel.Services?displayProperty=nameWithType>.|
|`Microsoft.IdentityModel.Web.Controls`|Non implementato in WIF 4.5|Le classi in `Microsoft.IdentityModel.Web.Controls` implementavano il controllo dell'accesso passivo federato, non esistente in WIF 4.5.|
|`Microsoft.IdentityModel.WindowsTokenService`|Non implementato in WIF 4.5|-|

## <a name="see-also"></a>Vedere anche

- [Novità di Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)
- [Linee guida per la migrazione di un'applicazione compilata con le versioni di WIF dalla 3.5 alla 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)
