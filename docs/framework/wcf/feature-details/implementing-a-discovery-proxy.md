---
title: Implementazione di un proxy di individuazione
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 382df95fef2108d338e4ea327da9185c856eca5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579241"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="a8ad0-102">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="a8ad0-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="a8ad0-103">Contenuto della sezione vengono descritti i passaggi necessari per implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="a8ad0-104">Un proxy di individuazione è un servizio autonomo che contiene un repository di servizi.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="a8ad0-105">I client possono eseguire una query su un proxy di individuazione per cercare servizi individuabili noti al proxy.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="a8ad0-106">La modalità di popolamento di un proxy con i servizi dipende dall'implementatore.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="a8ad0-107">Un proxy di individuazione può ad esempio connettersi a un repository del servizio esistente e può rendere individuabili tali informazioni, un amministratore può usare un'interfaccia API di gestione per aggiungere servizi individuabili a un proxy o un proxy di individuazione può usare la funzionalità degli annunci per aggiornare la cache interna.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="a8ad0-108">L'implementazione WCF fornisce classi di base che consentono di compilare con facilità un proxy.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="a8ad0-109">È possibile usare queste API per compilare un proxy di individuazione sul repository esistente.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="a8ad0-110">Il proxy di individuazione implementato è simile a qualsiasi altro servizio WCF. È infatti possibile renderlo individuabile e fare in modo che i client ne individuino gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8ad0-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a8ad0-111">In This Section</span></span>  
 [<span data-ttu-id="a8ad0-112">Procedura: implementare un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="a8ad0-112">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="a8ad0-113">Descrive come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="a8ad0-114">Procedura: implementare un servizio individuabile che esegue la registrazione al proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="a8ad0-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="a8ad0-115">Viene descritto come implementare un servizio WCF individuabile che esegue la registrazione con il proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-115">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="a8ad0-116">Procedura: implementare un'applicazione client che usa il proxy di individuazione per cercare un servizio</span><span class="sxs-lookup"><span data-stu-id="a8ad0-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="a8ad0-117">Viene descritto come implementare un'applicazione client WCF che utilizza il proxy di individuazione per cercare un servizio.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-117">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="a8ad0-118">Procedura: test del proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="a8ad0-118">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="a8ad0-119">Descrive come testare il codice scritto nei tre argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="a8ad0-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ad0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8ad0-120">See also</span></span>

- [<span data-ttu-id="a8ad0-121">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="a8ad0-121">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="a8ad0-122">Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a8ad0-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
