---
title: Chiamate non riuscite al secondo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e60ad3d7e9155eecfead38aca080a3044b0efce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="08b65-102">Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="08b65-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="08b65-103">Nome contatore: chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="08b65-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="08b65-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08b65-104">Description</span></span>  
 <span data-ttu-id="08b65-105">Numero di chiamate che hanno restituito errori a questa operazione al secondo.</span><span class="sxs-lookup"><span data-stu-id="08b65-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="08b65-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="08b65-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="08b65-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="08b65-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="08b65-108">Nelle applicazioni [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], le informazioni sugli errori di elaborazione vengono comunicate dai metodi di servizio tramite messaggi di errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="08b65-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="08b65-109">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="08b65-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="08b65-110">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="08b65-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b65-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08b65-111">See Also</span></span>  
 [<span data-ttu-id="08b65-112">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="08b65-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
