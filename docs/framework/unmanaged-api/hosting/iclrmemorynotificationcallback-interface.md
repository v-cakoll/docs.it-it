---
title: Interfaccia ICLRMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703809"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="0cd79-102">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="0cd79-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="0cd79-103">Consente all'host di segnalare le condizioni di utilizzo della memoria utilizzando un approccio simile a quello della `CreateMemoryResourceNotification` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="0cd79-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cd79-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0cd79-104">Methods</span></span>  
  
|<span data-ttu-id="0cd79-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0cd79-105">Method</span></span>|<span data-ttu-id="0cd79-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cd79-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cd79-107">Metodo OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="0cd79-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="0cd79-108">Notifica al Common Language Runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="0cd79-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cd79-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0cd79-109">Remarks</span></span>  
 <span data-ttu-id="0cd79-110">L'host utilizza l' `ICLRMemoryNotificationCallback` interfaccia per richiedere che le risorse di memoria di CLR siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="0cd79-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cd79-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cd79-111">Requirements</span></span>  
 <span data-ttu-id="0cd79-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cd79-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd79-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0cd79-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cd79-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0cd79-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cd79-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd79-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd79-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cd79-116">See also</span></span>

- [<span data-ttu-id="0cd79-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0cd79-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="0cd79-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="0cd79-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
