---
title: Implementazione di un proxy di individuazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ddea7bf69f697c5b9ecd9d41021bff2407522a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="0dc72-102">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="0dc72-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="0dc72-103">Contenuto della sezione vengono descritti i passaggi necessari per implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="0dc72-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="0dc72-104">Un proxy di individuazione è un servizio autonomo che contiene un repository di servizi.</span><span class="sxs-lookup"><span data-stu-id="0dc72-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="0dc72-105">I client possono eseguire una query su un proxy di individuazione per cercare servizi individuabili noti al proxy.</span><span class="sxs-lookup"><span data-stu-id="0dc72-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="0dc72-106">La modalità di popolamento di un proxy con i servizi dipende dall'implementatore.</span><span class="sxs-lookup"><span data-stu-id="0dc72-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="0dc72-107">Un proxy di individuazione può ad esempio connettersi a un repository del servizio esistente e può rendere individuabili tali informazioni, un amministratore può usare un'interfaccia API di gestione per aggiungere servizi individuabili a un proxy o un proxy di individuazione può usare la funzionalità degli annunci per aggiornare la cache interna.</span><span class="sxs-lookup"><span data-stu-id="0dc72-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="0dc72-108">L'implementazione WCF fornisce classi di base che consentono di compilare con facilità un proxy.</span><span class="sxs-lookup"><span data-stu-id="0dc72-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="0dc72-109">È possibile usare queste API per compilare un proxy di individuazione sul repository esistente.</span><span class="sxs-lookup"><span data-stu-id="0dc72-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="0dc72-110">Il proxy di individuazione implementato è simile a qualsiasi altro servizio WCF. È infatti possibile renderlo individuabile e fare in modo che i client ne individuino gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="0dc72-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dc72-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0dc72-111">In This Section</span></span>  
 [<span data-ttu-id="0dc72-112">Procedura: implementare un Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="0dc72-112">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="0dc72-113">Descrive come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="0dc72-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="0dc72-114">Procedura: implementare un servizio individuabile che esegue la registrazione con il Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="0dc72-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="0dc72-115">Descrive come implementare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] individuabile che esegue la registrazione al proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="0dc72-115">Describes how to implement a discoverable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="0dc72-116">Procedura: implementare un'applicazione Client che utilizza il Proxy di individuazione per trovare un servizio</span><span class="sxs-lookup"><span data-stu-id="0dc72-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="0dc72-117">Descrive come implementare un'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che usa il proxy di individuazione per cercare un servizio.</span><span class="sxs-lookup"><span data-stu-id="0dc72-117">Describes how to implement a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="0dc72-118">Procedura: testare il Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="0dc72-118">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="0dc72-119">Descrive come testare il codice scritto nei tre argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="0dc72-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc72-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dc72-120">See Also</span></span>  
 [<span data-ttu-id="0dc72-121">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="0dc72-121">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 [<span data-ttu-id="0dc72-122">Procedura: aggiungere a livello di programmazione esposizione al rilevamento a un servizio WCF e un Client</span><span class="sxs-lookup"><span data-stu-id="0dc72-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
