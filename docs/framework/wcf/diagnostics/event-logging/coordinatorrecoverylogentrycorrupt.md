---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121628"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="313e2-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="313e2-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="313e2-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="313e2-103">Id: 139</span></span>  
  
 <span data-ttu-id="313e2-104">Gravità: Error</span><span class="sxs-lookup"><span data-stu-id="313e2-104">Severity: Error</span></span>  
  
 <span data-ttu-id="313e2-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="313e2-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="313e2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="313e2-106">Description</span></span>  
 <span data-ttu-id="313e2-107">Questo evento indica che una voce del registro di ripristino del coordinatore è danneggiata e non può essere deserializzata.</span><span class="sxs-lookup"><span data-stu-id="313e2-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="313e2-108">L'errore può causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="313e2-108">Data loss may result from this error.</span></span> <span data-ttu-id="313e2-109">L'evento elenca l'ID transazione, i dati di ripristino (codifica Base64), l'eccezione, il nome processo e l'ID processo.</span><span class="sxs-lookup"><span data-stu-id="313e2-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313e2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="313e2-110">See also</span></span>

- [<span data-ttu-id="313e2-111">Registrazione eventi</span><span class="sxs-lookup"><span data-stu-id="313e2-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="313e2-112">Riferimenti generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="313e2-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
