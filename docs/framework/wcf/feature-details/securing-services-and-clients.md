---
title: Protezione di servizi e client
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: e455c7a48e1484d5acdcc5f6cdc9098997a3ba83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120731"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="721b2-102">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="721b2-102">Securing Services and Clients</span></span>
<span data-ttu-id="721b2-103">Le informazioni contenute in questa sezione è incentrata sulla programmazione della protezione in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="721b2-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="721b2-104">Quest'attività include, in genere, la selezione di un'associazione fornita dal sistema appropriata, l'impostazione delle proprietà dell'elemento di sicurezza e quindi l'impostazione delle proprietà dei comportamenti del servizio che regolano la modalità di recupero delle credenziali che devono essere usate dal servizio o dal client.</span><span class="sxs-lookup"><span data-stu-id="721b2-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="721b2-105">Queste tecniche soddisfano i requisiti di sicurezza della maggior parte degli utenti per la maggior parte degli scenari, come illustrato nella [scenari di sicurezza comuni](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="721b2-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="721b2-106">Se lo scenario richiede altre funzionalità, vedere innanzitutto [funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); se una soluzione non è evidente, vedere [estensione di sicurezza](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="721b2-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="721b2-107">Se si sta creando (o interagisce con) un sistema che usa attestazioni dettagliate, vedere gli argomenti in [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="721b2-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="721b2-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="721b2-108">In This Section</span></span>  
 [<span data-ttu-id="721b2-109">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="721b2-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="721b2-110">Panoramica del modello di programmazione usato per proteggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="721b2-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="721b2-111">Panoramica della sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="721b2-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="721b2-112">Panoramica delle modalità di sicurezza dei messaggi tramite il livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="721b2-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="721b2-113">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="721b2-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="721b2-114">Riepilogo dei motivi per l'uso di sicurezza a livello di messaggio in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="721b2-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="721b2-115">Sessioni sicure</span><span class="sxs-lookup"><span data-stu-id="721b2-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="721b2-116">Una descrizione delle considerazioni necessarie per la protezione di una sessione WCF.</span><span class="sxs-lookup"><span data-stu-id="721b2-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="721b2-117">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="721b2-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="721b2-118">Spiegazione di alcune delle attività comuni necessarie quando si usano certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="721b2-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="721b2-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="721b2-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="721b2-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="721b2-120">Related Sections</span></span>  
 [<span data-ttu-id="721b2-121">Concetti relativi alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="721b2-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="721b2-122">Estensione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="721b2-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="721b2-123">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="721b2-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="721b2-124">Associazioni e sicurezza</span><span class="sxs-lookup"><span data-stu-id="721b2-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="721b2-125">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="721b2-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="721b2-126">Estensione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="721b2-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="721b2-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="721b2-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="721b2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="721b2-128">See also</span></span>

- [<span data-ttu-id="721b2-129">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="721b2-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="721b2-130">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="721b2-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
