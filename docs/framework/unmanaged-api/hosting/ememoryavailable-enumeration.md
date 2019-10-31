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
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134298"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="21494-102">Enumerazione EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="21494-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="21494-103">Contiene valori che indicano la quantità di memoria fisica disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="21494-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="21494-104">Questi valori vengono mappati logicamente agli eventi per la memoria alta e bassa restituita dalla funzione `CreateMemoryResourceNotification` nell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="21494-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21494-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21494-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="21494-106">Members</span><span class="sxs-lookup"><span data-stu-id="21494-106">Members</span></span>  
  
|<span data-ttu-id="21494-107">Member</span><span class="sxs-lookup"><span data-stu-id="21494-107">Member</span></span>|<span data-ttu-id="21494-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21494-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="21494-109">È disponibile molta memoria fisica.</span><span class="sxs-lookup"><span data-stu-id="21494-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="21494-110">È disponibile una quantità di memoria fisica minima.</span><span class="sxs-lookup"><span data-stu-id="21494-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="21494-111">La memoria fisica disponibile è neutra.</span><span class="sxs-lookup"><span data-stu-id="21494-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21494-112">Note</span><span class="sxs-lookup"><span data-stu-id="21494-112">Remarks</span></span>  
 <span data-ttu-id="21494-113">Questo valore viene passato dall'host al Common Language Runtime (CLR) utilizzando una chiamata al metodo [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="21494-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21494-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21494-114">Requirements</span></span>  
 <span data-ttu-id="21494-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21494-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21494-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="21494-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21494-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21494-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21494-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21494-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21494-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21494-119">See also</span></span>

- [<span data-ttu-id="21494-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="21494-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
