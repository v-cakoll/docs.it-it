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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae2b8a8bb536d914edd6c7154136867caee553b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="f07ba-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="f07ba-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="f07ba-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="f07ba-103">Id: 139</span></span>  
  
 <span data-ttu-id="f07ba-104">Gravità: errore</span><span class="sxs-lookup"><span data-stu-id="f07ba-104">Severity: Error</span></span>  
  
 <span data-ttu-id="f07ba-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="f07ba-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="f07ba-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f07ba-106">Description</span></span>  
 <span data-ttu-id="f07ba-107">Questo evento indica che una voce del registro di ripristino del coordinatore è danneggiata e non può essere deserializzata.</span><span class="sxs-lookup"><span data-stu-id="f07ba-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="f07ba-108">L'errore può causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="f07ba-108">Data loss may result from this error.</span></span> <span data-ttu-id="f07ba-109">L'evento elenca l'ID transazione, i dati di ripristino (codifica Base64), l'eccezione, il nome processo e l'ID processo.</span><span class="sxs-lookup"><span data-stu-id="f07ba-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07ba-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f07ba-110">See Also</span></span>  
 [<span data-ttu-id="f07ba-111">Registrazione eventi</span><span class="sxs-lookup"><span data-stu-id="f07ba-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="f07ba-112">Riferimenti generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="f07ba-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
