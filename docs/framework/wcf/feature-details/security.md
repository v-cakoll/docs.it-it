---
title: Funzionalità di sicurezza di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 327fb509a5186a0b3f428efc2ddd7f983bcfa978
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595144"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="369ff-102">Funzionalità di sicurezza di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="369ff-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="369ff-103">Negli argomenti di questa sezione vengono descritte le funzionalità di sicurezza di Windows Communication Foundation (WCF) e viene illustrato come utilizzarle per proteggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="369ff-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="369ff-104">Per ulteriori informazioni su Windows Server AppFabric e sulla sicurezza, vedere [modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10)) .</span><span class="sxs-lookup"><span data-stu-id="369ff-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="369ff-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="369ff-105">In This Section</span></span>  
 [<span data-ttu-id="369ff-106">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="369ff-106">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="369ff-107">Vengono descritte le funzionalità di sicurezza di WCF.</span><span class="sxs-lookup"><span data-stu-id="369ff-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="369ff-108">Concetti relativi alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="369ff-108">Security Concepts</span></span>](security-concepts.md)  
 <span data-ttu-id="369ff-109">Vengono descritti i concetti e la terminologia di base utilizzati nella sicurezza di WCF.</span><span class="sxs-lookup"><span data-stu-id="369ff-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="369ff-110">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="369ff-110">Common Security Scenarios</span></span>](common-security-scenarios.md)  
 <span data-ttu-id="369ff-111">Vengono descritti gli scenari e le topologie che è possibile configurare con WCF.</span><span class="sxs-lookup"><span data-stu-id="369ff-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="369ff-112">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="369ff-112">Security Behaviors</span></span>](security-behaviors-in-wcf.md)  
 <span data-ttu-id="369ff-113">Fornisce cenni preliminari su comportamenti WCF che influiscono sulla sicurezza, ad esempio l'impostazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="369ff-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="369ff-114">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="369ff-114">Bindings and Security</span></span>](bindings-and-security.md)  
 <span data-ttu-id="369ff-115">Vengono forniti vari argomenti che descrivono le funzionalità di sicurezza relative alle associazioni. In particolare, vengono forniti argomenti che descrivono come creare associazioni di sicurezza personalizzate.</span><span class="sxs-lookup"><span data-stu-id="369ff-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="369ff-116">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="369ff-116">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
 <span data-ttu-id="369ff-117">Viene descritto come proteggere i messaggi utilizzando le funzionalità di sicurezza di WCF.</span><span class="sxs-lookup"><span data-stu-id="369ff-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="369ff-118">autenticazione</span><span class="sxs-lookup"><span data-stu-id="369ff-118">Authentication</span></span>](authentication-in-wcf.md)  
 <span data-ttu-id="369ff-119">Vengono illustrate alcune attività comuni di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="369ff-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="369ff-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="369ff-120">Authorization</span></span>](authorization-in-wcf.md)  
 <span data-ttu-id="369ff-121">Vengono descritti alcuni scenari comuni di autorizzazione contenenti implementazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="369ff-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="369ff-122">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="369ff-122">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
 <span data-ttu-id="369ff-123">Vengono descritti i concetti di base della federazione e viene fornita la procedura per creare client che comunicano con server federati.</span><span class="sxs-lookup"><span data-stu-id="369ff-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="369ff-124">Attendibilità parziale</span><span class="sxs-lookup"><span data-stu-id="369ff-124">Partial Trust</span></span>](partial-trust.md)  
 <span data-ttu-id="369ff-125">Viene descritto come eseguire scenari parzialmente attendibili e limitazioni di WCF durante l'esecuzione parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="369ff-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="369ff-126">Controllo</span><span class="sxs-lookup"><span data-stu-id="369ff-126">Auditing</span></span>](auditing-security-events.md)  
 <span data-ttu-id="369ff-127">Viene descritto come controllare gli eventi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="369ff-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="369ff-128">Indicazioni di sicurezza e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="369ff-128">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
 <span data-ttu-id="369ff-129">Linee guida per la creazione di applicazioni WCF sicure.</span><span class="sxs-lookup"><span data-stu-id="369ff-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="369ff-130">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="369ff-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="369ff-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="369ff-131">Related Sections</span></span>  
 [<span data-ttu-id="369ff-132">Dettagli delle funzionalità di WCF</span><span class="sxs-lookup"><span data-stu-id="369ff-132">WCF Feature Details</span></span>](index.md)  
  
 [<span data-ttu-id="369ff-133">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="369ff-133">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="369ff-134">Esercitazione Introduzione</span><span class="sxs-lookup"><span data-stu-id="369ff-134">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)  
  
 [<span data-ttu-id="369ff-135">Panoramica concettuale</span><span class="sxs-lookup"><span data-stu-id="369ff-135">Conceptual Overview</span></span>](../conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="369ff-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="369ff-136">See also</span></span>

- [<span data-ttu-id="369ff-137">Configurazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="369ff-137">Configuring Your Application</span></span>](../diagnostics/configuring-your-application.md)
