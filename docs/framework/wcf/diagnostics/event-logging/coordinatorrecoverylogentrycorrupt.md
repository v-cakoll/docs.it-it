---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 0dc74b784d8a9ed3ab27bb4b8d3de34143f6ce07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639484"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="31392-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="31392-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="31392-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="31392-103">Id: 139</span></span>  
  
 <span data-ttu-id="31392-104">Gravità: Error</span><span class="sxs-lookup"><span data-stu-id="31392-104">Severity: Error</span></span>  
  
 <span data-ttu-id="31392-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="31392-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="31392-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31392-106">Description</span></span>  
 <span data-ttu-id="31392-107">Questo evento indica che una voce del registro di ripristino del coordinatore è danneggiata e non può essere deserializzata.</span><span class="sxs-lookup"><span data-stu-id="31392-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="31392-108">L'errore può causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="31392-108">Data loss may result from this error.</span></span> <span data-ttu-id="31392-109">L'evento elenca l'ID transazione, i dati di ripristino (codifica Base64), l'eccezione, il nome processo e l'ID processo.</span><span class="sxs-lookup"><span data-stu-id="31392-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31392-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31392-110">See also</span></span>
- [<span data-ttu-id="31392-111">Registrazione eventi</span><span class="sxs-lookup"><span data-stu-id="31392-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="31392-112">Riferimenti generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="31392-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
