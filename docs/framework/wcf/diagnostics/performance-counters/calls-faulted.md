---
title: Chiamate con errori
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb9e8045-6aeb-4b7f-a825-8283c44252a1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23016861eb5385d8383a68e90e23211aec4bde38
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="calls-faulted"></a><span data-ttu-id="13b31-102">Chiamate con errori</span><span class="sxs-lookup"><span data-stu-id="13b31-102">Calls Faulted</span></span>
<span data-ttu-id="13b31-103">Nome contatore: chiamate con errori</span><span class="sxs-lookup"><span data-stu-id="13b31-103">Counter Name: Calls Faulted</span></span>  
  
## <a name="description"></a><span data-ttu-id="13b31-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13b31-104">Description</span></span>  
 <span data-ttu-id="13b31-105">Numero di chiamate a questa operazione che hanno restituito errori.</span><span class="sxs-lookup"><span data-stu-id="13b31-105">Number of calls to this operation that returned faults.</span></span> <span data-ttu-id="13b31-106">Nelle applicazioni [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], le informazioni sugli errori di elaborazione vengono comunicate dai metodi di servizio tramite messaggi di errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="13b31-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="13b31-107">Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva.</span><span class="sxs-lookup"><span data-stu-id="13b31-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="13b31-108">Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.</span><span class="sxs-lookup"><span data-stu-id="13b31-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b31-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13b31-109">See Also</span></span>  
 [<span data-ttu-id="13b31-110">Specifica e gestione degli errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="13b31-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
