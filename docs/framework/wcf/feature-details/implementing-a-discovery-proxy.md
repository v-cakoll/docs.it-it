---
title: Implementazione di un proxy di individuazione
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 5d9296d8ba70d4c9e8d8339fa3a032d9c4c62826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047061"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="35a46-102">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="35a46-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="35a46-103">Contenuto della sezione vengono descritti i passaggi necessari per implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="35a46-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="35a46-104">Un proxy di individuazione è un servizio autonomo che contiene un repository di servizi.</span><span class="sxs-lookup"><span data-stu-id="35a46-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="35a46-105">I client possono eseguire una query su un proxy di individuazione per cercare servizi individuabili noti al proxy.</span><span class="sxs-lookup"><span data-stu-id="35a46-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="35a46-106">La modalità di popolamento di un proxy con i servizi dipende dall'implementatore.</span><span class="sxs-lookup"><span data-stu-id="35a46-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="35a46-107">Un proxy di individuazione può ad esempio connettersi a un repository del servizio esistente e può rendere individuabili tali informazioni, un amministratore può usare un'interfaccia API di gestione per aggiungere servizi individuabili a un proxy o un proxy di individuazione può usare la funzionalità degli annunci per aggiornare la cache interna.</span><span class="sxs-lookup"><span data-stu-id="35a46-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="35a46-108">L'implementazione WCF fornisce classi di base che consentono di compilare con facilità un proxy.</span><span class="sxs-lookup"><span data-stu-id="35a46-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="35a46-109">È possibile usare queste API per compilare un proxy di individuazione sul repository esistente.</span><span class="sxs-lookup"><span data-stu-id="35a46-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="35a46-110">Il proxy di individuazione implementato è simile a qualsiasi altro servizio WCF. È infatti possibile renderlo individuabile e fare in modo che i client ne individuino gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="35a46-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35a46-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="35a46-111">In This Section</span></span>  
 [<span data-ttu-id="35a46-112">Procedura: Implementare un Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="35a46-112">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="35a46-113">Descrive come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="35a46-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="35a46-114">Procedura: Implementare un servizio individuabile che esegue la registrazione al Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="35a46-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="35a46-115">Viene descritto come implementare un servizio WCF individuabile che esegue la registrazione al proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="35a46-115">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="35a46-116">Procedura: Implementare un'applicazione Client che usa il Proxy di individuazione per cercare un servizio</span><span class="sxs-lookup"><span data-stu-id="35a46-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="35a46-117">Viene descritto come implementare un'applicazione client WCF che usa il proxy di individuazione per eseguire la ricerca per un servizio.</span><span class="sxs-lookup"><span data-stu-id="35a46-117">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="35a46-118">Procedura: Testare il Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="35a46-118">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="35a46-119">Descrive come testare il codice scritto nei tre argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="35a46-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a46-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35a46-120">See also</span></span>

- [<span data-ttu-id="35a46-121">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="35a46-121">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [<span data-ttu-id="35a46-122">Procedura: A livello di codice aggiungere funzionalità di individuazione a un Client e servizio WCF</span><span class="sxs-lookup"><span data-stu-id="35a46-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
