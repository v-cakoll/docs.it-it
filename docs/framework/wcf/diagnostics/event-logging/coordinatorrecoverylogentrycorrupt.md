---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797981"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="0f199-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="0f199-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="0f199-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="0f199-103">Id: 139</span></span>  
  
 <span data-ttu-id="0f199-104">Gravità: Errore</span><span class="sxs-lookup"><span data-stu-id="0f199-104">Severity: Error</span></span>  
  
 <span data-ttu-id="0f199-105">Categoria: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="0f199-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="0f199-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f199-106">Description</span></span>  
 <span data-ttu-id="0f199-107">Questo evento indica che una voce del registro di ripristino del coordinatore è danneggiata e non può essere deserializzata.</span><span class="sxs-lookup"><span data-stu-id="0f199-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="0f199-108">L'errore può causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="0f199-108">Data loss may result from this error.</span></span> <span data-ttu-id="0f199-109">L'evento elenca l'ID transazione, i dati di ripristino (codifica Base64), l'eccezione, il nome processo e l'ID processo.</span><span class="sxs-lookup"><span data-stu-id="0f199-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f199-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f199-110">See also</span></span>

- [<span data-ttu-id="0f199-111">Registrazione eventi</span><span class="sxs-lookup"><span data-stu-id="0f199-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="0f199-112">Riferimenti generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="0f199-112">Events General Reference</span></span>](events-general-reference.md)
