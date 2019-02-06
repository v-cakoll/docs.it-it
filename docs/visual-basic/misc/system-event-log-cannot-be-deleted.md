---
title: Non è possibile eliminare il registro eventi di sistema
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: 7c2d03b0e9c27c0cc935963251006cfe83f11aba
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739124"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="c36f7-102">Non è possibile eliminare il registro eventi di sistema</span><span class="sxs-lookup"><span data-stu-id="c36f7-102">System event log cannot be deleted</span></span>
<span data-ttu-id="c36f7-103">Si è provato a eliminare il registro eventi di sistema, che non può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="c36f7-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="c36f7-104">Il registro di sistema tiene traccia degli eventi di sistema come gli errori relativi all'avvio del sistema e all'hardware.</span><span class="sxs-lookup"><span data-stu-id="c36f7-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c36f7-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c36f7-105">To correct this error</span></span>  
  
-   <span data-ttu-id="c36f7-106">È consigliabile che l'applicazione scriva in un registro applicazioni o in un registro personalizzato anziché nel registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="c36f7-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
-   <span data-ttu-id="c36f7-107">Non tentare di eliminare il registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="c36f7-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36f7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c36f7-108">See also</span></span>
- <span data-ttu-id="c36f7-109">[Gestione dei log eventi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c36f7-109">[Administering Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="c36f7-110">[Procedura: Creare e rimuovere i log eventi personalizzati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c36f7-110">[How to: Create and Remove Custom Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span></span>
