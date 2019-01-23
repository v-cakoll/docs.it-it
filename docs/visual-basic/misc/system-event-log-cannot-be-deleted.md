---
title: Non è possibile eliminare il registro eventi di sistema
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: adae713306412ffa315ed6a5ccc990e81835552f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509564"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="8170e-102">Non è possibile eliminare il registro eventi di sistema</span><span class="sxs-lookup"><span data-stu-id="8170e-102">System event log cannot be deleted</span></span>
<span data-ttu-id="8170e-103">Si è provato a eliminare il registro eventi di sistema, che non può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="8170e-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="8170e-104">Il registro di sistema tiene traccia degli eventi di sistema come gli errori relativi all'avvio del sistema e all'hardware.</span><span class="sxs-lookup"><span data-stu-id="8170e-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8170e-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8170e-105">To correct this error</span></span>  
  
-   <span data-ttu-id="8170e-106">È consigliabile che l'applicazione scriva in un registro applicazioni o in un registro personalizzato anziché nel registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="8170e-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
-   <span data-ttu-id="8170e-107">Non tentare di eliminare il registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="8170e-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8170e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8170e-108">See also</span></span>
- [<span data-ttu-id="8170e-109">Gestione dei log eventi</span><span class="sxs-lookup"><span data-stu-id="8170e-109">Administering Event Logs</span></span>](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)
- [<span data-ttu-id="8170e-110">Procedura: Creare e rimuovere i log eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="8170e-110">How to: Create and Remove Custom Event Logs</span></span>](https://msdn.microsoft.com/library/af9b7da0-80c7-46ac-b7f7-897063ddd503)
