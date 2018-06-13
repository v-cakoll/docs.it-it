---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3f51d1269f5ca89f4f02257c8accef3423aa7eb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472683"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="d33e9-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="d33e9-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="d33e9-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="d33e9-103">Id: 139</span></span>  
  
 <span data-ttu-id="d33e9-104">Gravità: errore</span><span class="sxs-lookup"><span data-stu-id="d33e9-104">Severity: Error</span></span>  
  
 <span data-ttu-id="d33e9-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="d33e9-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="d33e9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d33e9-106">Description</span></span>  
 <span data-ttu-id="d33e9-107">Questo evento indica che una voce del registro di ripristino del coordinatore è danneggiata e non può essere deserializzata.</span><span class="sxs-lookup"><span data-stu-id="d33e9-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="d33e9-108">L'errore può causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="d33e9-108">Data loss may result from this error.</span></span> <span data-ttu-id="d33e9-109">L'evento elenca l'ID transazione, i dati di ripristino (codifica Base64), l'eccezione, il nome processo e l'ID processo.</span><span class="sxs-lookup"><span data-stu-id="d33e9-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33e9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d33e9-110">See Also</span></span>  
 [<span data-ttu-id="d33e9-111">Registrazione eventi</span><span class="sxs-lookup"><span data-stu-id="d33e9-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="d33e9-112">Riferimenti generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="d33e9-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
