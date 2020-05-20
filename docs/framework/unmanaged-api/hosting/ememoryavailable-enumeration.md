---
title: Enumerazione EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 822396e28d000a5309738680fec502e1aeacd67c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616216"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="eefc9-102">Enumerazione EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="eefc9-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="eefc9-103">Contiene valori che indicano la quantità di memoria fisica disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="eefc9-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="eefc9-104">Questi valori vengono mappati logicamente agli eventi per la memoria alta e bassa restituita dalla `CreateMemoryResourceNotification` funzione nell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="eefc9-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefc9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eefc9-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="eefc9-106">Membri</span><span class="sxs-lookup"><span data-stu-id="eefc9-106">Members</span></span>  
  
|<span data-ttu-id="eefc9-107">Membro</span><span class="sxs-lookup"><span data-stu-id="eefc9-107">Member</span></span>|<span data-ttu-id="eefc9-108">Description</span><span class="sxs-lookup"><span data-stu-id="eefc9-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="eefc9-109">È disponibile molta memoria fisica.</span><span class="sxs-lookup"><span data-stu-id="eefc9-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="eefc9-110">È disponibile una quantità di memoria fisica minima.</span><span class="sxs-lookup"><span data-stu-id="eefc9-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="eefc9-111">La memoria fisica disponibile è neutra.</span><span class="sxs-lookup"><span data-stu-id="eefc9-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eefc9-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eefc9-112">Remarks</span></span>  
 <span data-ttu-id="eefc9-113">Questo valore viene passato dall'host al Common Language Runtime (CLR) utilizzando una chiamata al metodo [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eefc9-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefc9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eefc9-114">Requirements</span></span>  
 <span data-ttu-id="eefc9-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefc9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefc9-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eefc9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eefc9-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eefc9-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eefc9-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefc9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefc9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eefc9-119">See also</span></span>

- [<span data-ttu-id="eefc9-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="eefc9-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
