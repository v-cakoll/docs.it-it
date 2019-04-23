---
title: Chiamate non riuscite al secondo
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: 5b7569b6a00757fbb863b90b25b44815a349ab07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115518"
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="f2a8b-102">Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="f2a8b-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="f2a8b-103">Nome contatore: Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="f2a8b-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f2a8b-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2a8b-104">Description</span></span>  
 <span data-ttu-id="f2a8b-105">Numero di chiamate che hanno restituito errori a questa operazione al secondo.</span><span class="sxs-lookup"><span data-stu-id="f2a8b-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="f2a8b-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="f2a8b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f2a8b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f2a8b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="f2a8b-108">Nelle applicazioni Windows Communication Foundation (WCF), informazioni sugli errori di elaborazione tramite messaggi di errore SOAP vengono comunicate dai metodi di servizio.</span><span class="sxs-lookup"><span data-stu-id="f2a8b-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="f2a8b-109">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="f2a8b-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="f2a8b-110">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="f2a8b-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a8b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2a8b-111">See also</span></span>

- [<span data-ttu-id="f2a8b-112">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="f2a8b-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
