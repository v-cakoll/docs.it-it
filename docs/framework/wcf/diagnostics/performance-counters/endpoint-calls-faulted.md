---
title: 'Endpoint: chiamate con errori'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62eb1ad10c7112696d8fa2a358db4c88ee86cb3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="4a9dc-102">Endpoint: chiamate con errori</span><span class="sxs-lookup"><span data-stu-id="4a9dc-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="4a9dc-103">Nome contatore: chiamate con errori</span><span class="sxs-lookup"><span data-stu-id="4a9dc-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4a9dc-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a9dc-104">Description</span></span>  
 <span data-ttu-id="4a9dc-105">Numero di chiamate a questo endpoint che hanno restituito errori.</span><span class="sxs-lookup"><span data-stu-id="4a9dc-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="4a9dc-106">Nelle applicazioni [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], le informazioni sugli errori di elaborazione vengono comunicate dai metodi di servizio tramite messaggi di errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="4a9dc-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="4a9dc-107">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="4a9dc-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="4a9dc-108">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="4a9dc-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9dc-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a9dc-109">See Also</span></span>  
 [<span data-ttu-id="4a9dc-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="4a9dc-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
