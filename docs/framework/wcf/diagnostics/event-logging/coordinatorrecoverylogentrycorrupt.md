---
title: CoordinatorRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1db6f8dc4136623f35767c122dbea46fd4706b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="b6752-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="b6752-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="b6752-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="b6752-103">Id: 139</span></span>  
  
 <span data-ttu-id="b6752-104">Gravità: errore</span><span class="sxs-lookup"><span data-stu-id="b6752-104">Severity: Error</span></span>  
  
 <span data-ttu-id="b6752-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="b6752-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6752-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6752-106">Description</span></span>  
 <span data-ttu-id="b6752-107">Questo evento indica che una voce del registro di ripristino del coordinatore è danneggiata e non può essere deserializzata.</span><span class="sxs-lookup"><span data-stu-id="b6752-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="b6752-108">L'errore può causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="b6752-108">Data loss may result from this error.</span></span> <span data-ttu-id="b6752-109">L'evento elenca l'ID transazione, i dati di ripristino (codifica Base64), l'eccezione, il nome processo e l'ID processo.</span><span class="sxs-lookup"><span data-stu-id="b6752-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6752-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6752-110">See Also</span></span>  
 [<span data-ttu-id="b6752-111">Registrazione degli eventi</span><span class="sxs-lookup"><span data-stu-id="b6752-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="b6752-112">Riferimenti generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="b6752-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
