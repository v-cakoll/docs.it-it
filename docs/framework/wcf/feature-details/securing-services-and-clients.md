---
title: Protezione di servizi e client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 52e07a83f5a1b84abc46f00e6fd6e80e4b9a2622
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="e331c-102">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e331c-102">Securing Services and Clients</span></span>
<span data-ttu-id="e331c-103">Le informazioni in questa sezione si concentrano sulla programmazione della protezione in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e331c-103">The information in this section focuses on programming security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="e331c-104">Quest'attività include, in genere, la selezione di un'associazione fornita dal sistema appropriata, l'impostazione delle proprietà dell'elemento di sicurezza e quindi l'impostazione delle proprietà dei comportamenti del servizio che regolano la modalità di recupero delle credenziali che devono essere usate dal servizio o dal client.</span><span class="sxs-lookup"><span data-stu-id="e331c-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="e331c-105">Queste tecniche di soddisfare i requisiti di sicurezza della maggior parte degli utenti per la maggior parte degli scenari, come illustrato nel [comuni scenari di sicurezza](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="e331c-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="e331c-106">Se lo scenario richiede altre funzionalità, vedere prima [funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); se una soluzione non è evidente, vedere [estensione sicurezza](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="e331c-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="e331c-107">Se Crea (o si interagisce con) un sistema che utilizza le attestazioni avanzate, vedere gli argomenti in [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="e331c-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e331c-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e331c-108">In This Section</span></span>  
 [<span data-ttu-id="e331c-109">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="e331c-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="e331c-110">Panoramica del modello di programmazione usato per proteggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="e331c-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="e331c-111">Panoramica della sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="e331c-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="e331c-112">Panoramica delle modalità di sicurezza dei messaggi tramite il livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="e331c-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="e331c-113">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="e331c-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="e331c-114">Riepilogo dei motivi per l'uso della protezione a livello di messaggio in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e331c-114">Summarizes reasons for using message-level security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
 [<span data-ttu-id="e331c-115">Sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="e331c-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="e331c-116">Descrizione delle considerazioni necessarie in caso di sicurezza di una sessione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e331c-116">A discussion of the considerations required when securing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] session.</span></span>  
  
 [<span data-ttu-id="e331c-117">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="e331c-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="e331c-118">Spiegazione di alcune delle attività comuni necessarie quando si usano certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="e331c-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e331c-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="e331c-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="e331c-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e331c-120">Related Sections</span></span>  
 [<span data-ttu-id="e331c-121">Concetti relativi alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="e331c-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="e331c-122">Estensione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e331c-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="e331c-123">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="e331c-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="e331c-124">Associazioni e sicurezza</span><span class="sxs-lookup"><span data-stu-id="e331c-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="e331c-125">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e331c-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="e331c-126">Estensione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e331c-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="e331c-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e331c-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="e331c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e331c-128">See Also</span></span>  
 [<span data-ttu-id="e331c-129">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="e331c-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="e331c-130">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="e331c-130">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
