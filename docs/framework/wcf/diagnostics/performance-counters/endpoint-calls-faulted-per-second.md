---
title: 'Endpoint: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: f1b2997a0f1e16c897fc319d1833313141f5c4bf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199596"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="0ead9-102">Endpoint: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="0ead9-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="0ead9-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="0ead9-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0ead9-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ead9-104">Description</span></span>  
 <span data-ttu-id="0ead9-105">Numero di chiamate a questo endpoint che hanno restituito errori in un secondo.</span><span class="sxs-lookup"><span data-stu-id="0ead9-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="0ead9-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="0ead9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0ead9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="0ead9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="0ead9-108">Nelle applicazioni Windows Communication Foundation (WCF), informazioni sugli errori di elaborazione tramite messaggi di errore SOAP vengono comunicate dai metodi di servizio.</span><span class="sxs-lookup"><span data-stu-id="0ead9-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="0ead9-109">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="0ead9-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="0ead9-110">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="0ead9-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ead9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ead9-111">See Also</span></span>  
 [<span data-ttu-id="0ead9-112">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="0ead9-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
