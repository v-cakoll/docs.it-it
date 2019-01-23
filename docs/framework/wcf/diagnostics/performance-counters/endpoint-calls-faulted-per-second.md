---
title: 'Endpoint: Chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: 3b5c881c4ce7772e197bfc1a5603636b0975143c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517656"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="6a790-102">Endpoint: Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="6a790-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="6a790-103">Nome contatore: Chiamate non riuscite al secondo.</span><span class="sxs-lookup"><span data-stu-id="6a790-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6a790-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a790-104">Description</span></span>  
 <span data-ttu-id="6a790-105">Numero di chiamate a questo endpoint che hanno restituito errori in un secondo.</span><span class="sxs-lookup"><span data-stu-id="6a790-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="6a790-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="6a790-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6a790-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6a790-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="6a790-108">Nelle applicazioni Windows Communication Foundation (WCF), informazioni sugli errori di elaborazione tramite messaggi di errore SOAP vengono comunicate dai metodi di servizio.</span><span class="sxs-lookup"><span data-stu-id="6a790-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="6a790-109">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="6a790-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="6a790-110">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="6a790-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a790-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a790-111">See also</span></span>
- [<span data-ttu-id="6a790-112">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="6a790-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
