---
title: Informazioni di riferimento sulle API WIF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
caps.latest.revision: 4
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ef439ff502fc39074d36f63d139fd23e42471d42
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="wif-api-reference"></a>Informazioni di riferimento sulle API WIF
Le classi WIF (Windows Identity Foundation) sono suddivise tra questi assembly: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) e `System.ServiceModel` (System.ServiceModel.dll). Questo argomento fornisce collegamenti agli spazi dei nomi WIF e una breve spiegazione delle classi contenute in ogni spazio dei nomi.  
  
> [!IMPORTANT]
>  Questi spazi dei nomi `System.IdentityModel` contengono classi che implementano il modello di identità basato sulle attestazioni di WCF: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> e <xref:System.IdentityModel.Selectors?displayProperty=fullName>. A partire da .NET Framework 4.5, il modello di identità basata sulle attestazioni WCF è stato sostituito da WIF. Non usare le classi in questi tre spazi dei nomi per la compilazione di soluzioni basate su WIF.  
  
 <xref:System.IdentityModel?displayProperty=fullName>  
 Contiene le classi che rappresentano trasformazioni dei cookie, servizi token di sicurezza e lettori di dizionario XML specializzati.  
  
 <xref:System.IdentityModel.Configuration?displayProperty=fullName>  
 Contiene le classi che forniscono la configurazione per le applicazioni e i servizi creati con Windows Identity Foundation (WIF). Le classi in questo spazio dei nomi rappresentano le impostazioni nell'elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).  
  
 <xref:System.IdentityModel.Metadata?displayProperty=fullName>  
 Contiene le classi che rappresentano gli elementi in un documento di metadati della federazione.  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>  
 Contiene le classi che rappresentano elementi WS-Trust.  
  
 <xref:System.IdentityModel.Services?displayProperty=fullName>  
 Contiene le classi usate in scenari passivi (WS-Federation). Contiene anche alcune classi che rappresentano le impostazioni nell'elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Le impostazioni in questo elemento configurano WS-Federation per le applicazioni. Lo spazio dei nomi `System.IdentityModel.Services.Configuration` contiene la maggior parte delle classi usate per configurare WS-Federation.  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>  
 Contiene le classi che forniscono la configurazione per le applicazioni WIF che usano il protocollo WS-Federation. Le classi in questo spazio dei nomi rappresentano le impostazioni nell'elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Lo spazio dei nomi `System.IdentityModel.Services` contiene anche alcune classi usate per configurare WS-Federation.  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=fullName>  
 Contiene i gestori di token di sicurezza specializzati per scenari Web farm.  
  
 <xref:System.IdentityModel.Tokens?displayProperty=fullName>  
 Contiene le classi che rappresentano token di sicurezza, gestori di token di sicurezza e altri elementi token di sicurezza.  
  
 <xref:System.Security.Claims?displayProperty=fullName>  
 Contiene le classi che rappresentano attestazioni, identità basate sulle attestazioni, entità basate sulle attestazioni e altri elementi modello di identità basati sulle attestazioni.  
  
 <xref:System.ServiceModel.Security?displayProperty=fullName>  
 Contiene le classi che rappresentano contratti, canali, host servizio e altri elementi WCF usati in scenari attivi (WS-Trust). Questo spazio dei nomi contiene anche classi specifiche di Windows Communication Foundation (WCF) non usate da WIF.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento per la configurazione di WIF](../../../docs/framework/security/wif-configuration-reference.md)   
 [Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)

