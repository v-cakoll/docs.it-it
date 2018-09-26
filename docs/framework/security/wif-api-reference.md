---
title: Riferimento per le API di WPF
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
ms.openlocfilehash: 0cd373ae3fd5acb1650f0d8614b34c5d19cf9016
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195480"
---
# <a name="wif-api-reference"></a>Riferimento per le API di WPF
Le classi WIF (Windows Identity Foundation) sono suddivise tra questi assembly: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) e `System.ServiceModel` (System.ServiceModel.dll). Questo argomento fornisce collegamenti agli spazi dei nomi WIF e una breve spiegazione delle classi contenute in ogni spazio dei nomi.  
  
> [!IMPORTANT]
>  Questi spazi dei nomi `System.IdentityModel` contengono classi che implementano il modello di identità basato sulle attestazioni di WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> e <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. A partire da .NET Framework 4.5, il modello di identità basata sulle attestazioni WCF è stato sostituito da WIF. Non usare le classi in questi tre spazi dei nomi per la compilazione di soluzioni basate su WIF.  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 Contiene le classi che rappresentano trasformazioni dei cookie, servizi token di sicurezza e lettori di dizionario XML specializzati.  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 Contiene le classi che forniscono la configurazione per le applicazioni e i servizi creati con Windows Identity Foundation (WIF). Le classi in questo spazio dei nomi rappresentano le impostazioni nell'elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 Contiene le classi che rappresentano gli elementi in un documento di metadati della federazione.  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 Contiene le classi che rappresentano elementi WS-Trust.  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 Contiene le classi usate in scenari passivi (WS-Federation). Contiene anche alcune classi che rappresentano le impostazioni nell'elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Le impostazioni in questo elemento configurano WS-Federation per le applicazioni. Lo spazio dei nomi `System.IdentityModel.Services.Configuration` contiene la maggior parte delle classi usate per configurare WS-Federation.  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 Contiene le classi che forniscono la configurazione per le applicazioni WIF che usano il protocollo WS-Federation. Le classi in questo spazio dei nomi rappresentano le impostazioni nell'elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Lo spazio dei nomi `System.IdentityModel.Services` contiene anche alcune classi usate per configurare WS-Federation.  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 Contiene i gestori di token di sicurezza specializzati per scenari Web farm.  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 Contiene le classi che rappresentano token di sicurezza, gestori di token di sicurezza e altri elementi token di sicurezza.  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 Contiene le classi che rappresentano attestazioni, identità basate sulle attestazioni, entità basate sulle attestazioni e altri elementi modello di identità basati sulle attestazioni.  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 Contiene le classi che rappresentano contratti, canali, host servizio e altri elementi WCF usati in scenari attivi (WS-Trust). Questo spazio dei nomi contiene anche classi specifiche di Windows Communication Foundation (WCF) non usate da WIF.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento per la configurazione di WIF](../../../docs/framework/security/wif-configuration-reference.md)  
 [Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
