---
title: 'Servizio: Chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: 595b623d70bad82ea39ab3ef93fb5fd499268ff2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088476"
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="7ee55-102">Servizio: Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="7ee55-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="7ee55-103">Nome contatore: Chiamate non riuscite al secondo.</span><span class="sxs-lookup"><span data-stu-id="7ee55-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7ee55-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ee55-104">Description</span></span>  
 <span data-ttu-id="7ee55-105">Numero di chiamate a questo servizio che hanno restituito errori in un secondo.</span><span class="sxs-lookup"><span data-stu-id="7ee55-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="7ee55-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="7ee55-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7ee55-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7ee55-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="7ee55-108">Nelle applicazioni Windows Communication Foundation (WCF), informazioni sugli errori di elaborazione tramite messaggi di errore SOAP vengono comunicate dai metodi di servizio.</span><span class="sxs-lookup"><span data-stu-id="7ee55-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="7ee55-109">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="7ee55-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="7ee55-110">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="7ee55-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee55-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ee55-111">See also</span></span>

- [<span data-ttu-id="7ee55-112">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="7ee55-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
