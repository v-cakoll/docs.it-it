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
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176435"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="6ea90-102">Enumerazione EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="6ea90-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="6ea90-103">Contiene valori che indicano la quantità di memoria fisica libera nel computer.</span><span class="sxs-lookup"><span data-stu-id="6ea90-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="6ea90-104">Questi valori mappano logicamente agli eventi per la `CreateMemoryResourceNotification` memoria alta e bassa restituita dalla funzione nell'API di Windows.</span><span class="sxs-lookup"><span data-stu-id="6ea90-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea90-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ea90-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="6ea90-106">Members</span><span class="sxs-lookup"><span data-stu-id="6ea90-106">Members</span></span>  
  
|<span data-ttu-id="6ea90-107">Membro</span><span class="sxs-lookup"><span data-stu-id="6ea90-107">Member</span></span>|<span data-ttu-id="6ea90-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ea90-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="6ea90-109">È disponibile un'molta memoria fisica.</span><span class="sxs-lookup"><span data-stu-id="6ea90-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="6ea90-110">Pochissima memoria fisica è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6ea90-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="6ea90-111">La memoria fisica disponibile è neutra.</span><span class="sxs-lookup"><span data-stu-id="6ea90-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea90-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6ea90-112">Remarks</span></span>  
 <span data-ttu-id="6ea90-113">Questo valore viene passato dall'host a Common Language Runtime (CLR) utilizzando una chiamata al metodo [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6ea90-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea90-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ea90-114">Requirements</span></span>  
 <span data-ttu-id="6ea90-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea90-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea90-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ea90-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ea90-117">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="6ea90-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ea90-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea90-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea90-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ea90-119">See also</span></span>

- [<span data-ttu-id="6ea90-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="6ea90-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
