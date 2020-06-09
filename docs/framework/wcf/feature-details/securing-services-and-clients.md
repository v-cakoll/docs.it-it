---
title: Protezione di servizi e client
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: db0a0dcfbe04a7b7dbfabfed59f9b8637d0a2797
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586208"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="0e069-102">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="0e069-102">Securing Services and Clients</span></span>
<span data-ttu-id="0e069-103">Le informazioni contenute in questa sezione sono incentrate sulla sicurezza della programmazione in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0e069-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="0e069-104">Quest'attività include, in genere, la selezione di un'associazione fornita dal sistema appropriata, l'impostazione delle proprietà dell'elemento di sicurezza e quindi l'impostazione delle proprietà dei comportamenti del servizio che regolano la modalità di recupero delle credenziali che devono essere usate dal servizio o dal client.</span><span class="sxs-lookup"><span data-stu-id="0e069-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="0e069-105">Queste tecniche coprono i requisiti di sicurezza della maggior parte degli utenti per la maggior parte degli scenari, come illustrato negli [scenari di sicurezza comuni](common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="0e069-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](common-security-scenarios.md).</span></span> <span data-ttu-id="0e069-106">Se lo scenario richiede più funzionalità, vedere innanzitutto [funzionalità di sicurezza con associazioni personalizzate](security-capabilities-with-custom-bindings.md). Se una soluzione non è evidente, vedere [estensione della sicurezza](../extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="0e069-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../extending/extending-security.md).</span></span> <span data-ttu-id="0e069-107">Se si crea o si interopera con un sistema che utilizza attestazioni avanzate, vedere gli argomenti in [autorizzazione](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="0e069-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e069-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0e069-108">In This Section</span></span>  
 [<span data-ttu-id="0e069-109">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="0e069-109">Programming WCF Security</span></span>](programming-wcf-security.md)  
 <span data-ttu-id="0e069-110">Panoramica del modello di programmazione usato per proteggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="0e069-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="0e069-111">Panoramica sulla sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="0e069-111">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="0e069-112">Panoramica delle modalità di sicurezza dei messaggi tramite il livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="0e069-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="0e069-113">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="0e069-113">Message Security</span></span>](message-security-in-wcf.md)  
 <span data-ttu-id="0e069-114">Riepiloga i motivi per l'utilizzo della sicurezza a livello di messaggio nel Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0e069-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="0e069-115">Sessioni protette</span><span class="sxs-lookup"><span data-stu-id="0e069-115">Secure Sessions</span></span>](secure-sessions.md)  
 <span data-ttu-id="0e069-116">Descrizione delle considerazioni necessarie per la protezione di una sessione WCF.</span><span class="sxs-lookup"><span data-stu-id="0e069-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="0e069-117">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="0e069-117">Working with Certificates</span></span>](working-with-certificates.md)  
 <span data-ttu-id="0e069-118">Spiegazione di alcune delle attività comuni necessarie quando si usano certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="0e069-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0e069-119">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="0e069-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="0e069-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0e069-120">Related Sections</span></span>  
 [<span data-ttu-id="0e069-121">Concetti relativi alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e069-121">Security Concepts</span></span>](security-concepts.md)  
  
 [<span data-ttu-id="0e069-122">Estensione della protezione</span><span class="sxs-lookup"><span data-stu-id="0e069-122">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="0e069-123">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="0e069-123">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
 [<span data-ttu-id="0e069-124">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="0e069-124">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="0e069-125">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="0e069-125">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="0e069-126">Estensione della protezione</span><span class="sxs-lookup"><span data-stu-id="0e069-126">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="0e069-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0e069-127">Authorization</span></span>](authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e069-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e069-128">See also</span></span>

- [<span data-ttu-id="0e069-129">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="0e069-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- <span data-ttu-id="0e069-130">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0e069-130">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
