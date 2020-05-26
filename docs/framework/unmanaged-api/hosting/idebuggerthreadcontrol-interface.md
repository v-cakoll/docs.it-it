---
title: Interfaccia IDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805283"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="d7d2f-102">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="d7d2f-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="d7d2f-103">Fornisce metodi per notificare all'host informazioni sul blocco e lo sblocco dei thread da parte dei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="d7d2f-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7d2f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7d2f-104">Methods</span></span>  
  
|<span data-ttu-id="d7d2f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7d2f-105">Method</span></span>|<span data-ttu-id="d7d2f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7d2f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7d2f-107">Metodo ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="d7d2f-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="d7d2f-108">Notifica all'host che il thread che sta inviando questo callback sta per bloccarsi nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="d7d2f-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="d7d2f-109">Metodo ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="d7d2f-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="d7d2f-110">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread bloccati.</span><span class="sxs-lookup"><span data-stu-id="d7d2f-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="d7d2f-111">Metodo StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="d7d2f-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="d7d2f-112">Notifica all'host che i servizi di debug stanno per iniziare a bloccare tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="d7d2f-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7d2f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7d2f-113">Requirements</span></span>  
 <span data-ttu-id="d7d2f-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7d2f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7d2f-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d7d2f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7d2f-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7d2f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7d2f-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7d2f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d2f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d2f-118">See also</span></span>

- [<span data-ttu-id="d7d2f-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d7d2f-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
