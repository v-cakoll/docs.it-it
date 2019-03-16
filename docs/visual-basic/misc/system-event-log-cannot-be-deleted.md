---
title: Non è possibile eliminare il registro eventi di sistema
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: 30be01d03a25c246eda2be69a6fbc05e5ff25672
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58048489"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="6efff-102">Non è possibile eliminare il registro eventi di sistema</span><span class="sxs-lookup"><span data-stu-id="6efff-102">System event log cannot be deleted</span></span>
<span data-ttu-id="6efff-103">Si è provato a eliminare il registro eventi di sistema, che non può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="6efff-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="6efff-104">Il registro di sistema tiene traccia degli eventi di sistema come gli errori relativi all'avvio del sistema e all'hardware.</span><span class="sxs-lookup"><span data-stu-id="6efff-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6efff-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="6efff-105">To correct this error</span></span>  
  
-   <span data-ttu-id="6efff-106">È consigliabile che l'applicazione scriva in un registro applicazioni o in un registro personalizzato anziché nel registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="6efff-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
-   <span data-ttu-id="6efff-107">Non tentare di eliminare il registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="6efff-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efff-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6efff-108">See also</span></span>

- <span data-ttu-id="6efff-109">[Gestione dei log eventi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6efff-109">[Administering Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="6efff-110">[Procedura: Creare e rimuovere i log eventi personalizzati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6efff-110">[How to: Create and Remove Custom Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span></span>
