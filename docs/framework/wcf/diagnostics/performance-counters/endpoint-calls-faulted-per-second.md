---
title: 'Endpoint: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: 84dabf1215a02133874f3a0a55578c684a3308d9
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319971"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="2e9d5-102">Endpoint: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="2e9d5-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="2e9d5-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="2e9d5-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e9d5-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e9d5-104">Description</span></span>  
 <span data-ttu-id="2e9d5-105">Numero di chiamate a questo endpoint che hanno restituito errori in un secondo.</span><span class="sxs-lookup"><span data-stu-id="2e9d5-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="2e9d5-106">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="2e9d5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2e9d5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2e9d5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="2e9d5-108">Nelle applicazioni Windows Communication Foundation (WCF) i metodi di servizio comunicano l'elaborazione delle informazioni sugli errori mediante messaggi di errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="2e9d5-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="2e9d5-109">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="2e9d5-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="2e9d5-110">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="2e9d5-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9d5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e9d5-111">See also</span></span>

- [<span data-ttu-id="2e9d5-112">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="2e9d5-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
