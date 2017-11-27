---
title: Riferimento per le API di WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d7ae7ef82d12c024441d01ef420bc9366e3c589d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="wif-api-reference"></a><span data-ttu-id="43abf-102">Riferimento per le API di WPF</span><span class="sxs-lookup"><span data-stu-id="43abf-102">WIF API Reference</span></span>
<span data-ttu-id="43abf-103">Le classi WIF (Windows Identity Foundation) sono suddivise tra questi assembly: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) e `System.ServiceModel` (System.ServiceModel.dll).</span><span class="sxs-lookup"><span data-stu-id="43abf-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="43abf-104">Questo argomento fornisce collegamenti agli spazi dei nomi WIF e una breve spiegazione delle classi contenute in ogni spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="43abf-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="43abf-105">Questi spazi dei nomi `System.IdentityModel` contengono classi che implementano il modello di identità basato sulle attestazioni di WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> e <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43abf-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43abf-106">A partire da .NET Framework 4.5, il modello di identità basata sulle attestazioni WCF è stato sostituito da WIF.</span><span class="sxs-lookup"><span data-stu-id="43abf-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="43abf-107">Non usare le classi in questi tre spazi dei nomi per la compilazione di soluzioni basate su WIF.</span><span class="sxs-lookup"><span data-stu-id="43abf-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-108">Contiene le classi che rappresentano trasformazioni dei cookie, servizi token di sicurezza e lettori di dizionario XML specializzati.</span><span class="sxs-lookup"><span data-stu-id="43abf-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-109">Contiene le classi che forniscono la configurazione per le applicazioni e i servizi creati con Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="43abf-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="43abf-110">Le classi in questo spazio dei nomi rappresentano le impostazioni nell'elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).</span><span class="sxs-lookup"><span data-stu-id="43abf-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-111">Contiene le classi che rappresentano gli elementi in un documento di metadati della federazione.</span><span class="sxs-lookup"><span data-stu-id="43abf-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-112">Contiene le classi che rappresentano elementi WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="43abf-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-113">Contiene le classi usate in scenari passivi (WS-Federation).</span><span class="sxs-lookup"><span data-stu-id="43abf-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="43abf-114">Contiene anche alcune classi che rappresentano le impostazioni nell'elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="43abf-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="43abf-115">Le impostazioni in questo elemento configurano WS-Federation per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="43abf-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="43abf-116">Lo spazio dei nomi `System.IdentityModel.Services.Configuration` contiene la maggior parte delle classi usate per configurare WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="43abf-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-117">Contiene le classi che forniscono la configurazione per le applicazioni WIF che usano il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="43abf-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="43abf-118">Le classi in questo spazio dei nomi rappresentano le impostazioni nell'elemento [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).</span><span class="sxs-lookup"><span data-stu-id="43abf-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="43abf-119">Lo spazio dei nomi `System.IdentityModel.Services` contiene anche alcune classi usate per configurare WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="43abf-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-120">Contiene i gestori di token di sicurezza specializzati per scenari Web farm.</span><span class="sxs-lookup"><span data-stu-id="43abf-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-121">Contiene le classi che rappresentano token di sicurezza, gestori di token di sicurezza e altri elementi token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="43abf-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-122">Contiene le classi che rappresentano attestazioni, identità basate sulle attestazioni, entità basate sulle attestazioni e altri elementi modello di identità basati sulle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="43abf-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="43abf-123">Contiene le classi che rappresentano contratti, canali, host servizio e altri elementi WCF usati in scenari attivi (WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="43abf-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="43abf-124">Questo spazio dei nomi contiene anche classi specifiche di Windows Communication Foundation (WCF) non usate da WIF.</span><span class="sxs-lookup"><span data-stu-id="43abf-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43abf-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43abf-125">See Also</span></span>  
 [<span data-ttu-id="43abf-126">Guida di riferimento per la configurazione di WIF</span><span class="sxs-lookup"><span data-stu-id="43abf-126">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)  
 [<span data-ttu-id="43abf-127">Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="43abf-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
