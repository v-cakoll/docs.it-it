---
title: 'Servizio: chiamate con errori'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f82558bdacbc36569329764aa1639c81146d9127
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-faulted"></a><span data-ttu-id="0f4ac-102">Servizio: chiamate con errori</span><span class="sxs-lookup"><span data-stu-id="0f4ac-102">Service: Calls Faulted</span></span>
<span data-ttu-id="0f4ac-103">Nome contatore: chiamate con errori</span><span class="sxs-lookup"><span data-stu-id="0f4ac-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0f4ac-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f4ac-104">Description</span></span>  
 <span data-ttu-id="0f4ac-105">Numero di chiamate a questo servizio che hanno restituito errori.</span><span class="sxs-lookup"><span data-stu-id="0f4ac-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="0f4ac-106">Nelle applicazioni [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], le informazioni sugli errori di elaborazione vengono comunicate dai metodi di servizio tramite messaggi di errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="0f4ac-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="0f4ac-107">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="0f4ac-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="0f4ac-108">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="0f4ac-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4ac-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f4ac-109">See Also</span></span>  
 [<span data-ttu-id="0f4ac-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="0f4ac-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
