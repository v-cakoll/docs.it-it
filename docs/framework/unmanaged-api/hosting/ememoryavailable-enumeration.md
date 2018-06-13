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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 139cf540617e278eeaae8a2a5acf10dd797d5d10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429886"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="c3438-102">Enumerazione EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="c3438-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="c3438-103">Contiene valori che indicano la quantità di memoria fisica disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="c3438-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="c3438-104">Questi valori sono logicamente associati agli eventi massimo e minimo della memoria restituita dal `CreateMemoryResourceNotification` funzione nell'API Win32.</span><span class="sxs-lookup"><span data-stu-id="c3438-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3438-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3438-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="c3438-106">Membri</span><span class="sxs-lookup"><span data-stu-id="c3438-106">Members</span></span>  
  
|<span data-ttu-id="c3438-107">Membro</span><span class="sxs-lookup"><span data-stu-id="c3438-107">Member</span></span>|<span data-ttu-id="c3438-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3438-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="c3438-109">Una notevole quantità di memoria fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3438-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="c3438-110">Poca memoria fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3438-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="c3438-111">La memoria fisica disponibile è neutra.</span><span class="sxs-lookup"><span data-stu-id="c3438-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3438-112">Note</span><span class="sxs-lookup"><span data-stu-id="c3438-112">Remarks</span></span>  
 <span data-ttu-id="c3438-113">Questo valore viene passato dall'host per common language runtime (CLR) tramite una chiamata al [:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="c3438-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3438-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3438-114">Requirements</span></span>  
 <span data-ttu-id="c3438-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3438-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3438-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c3438-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3438-117">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c3438-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3438-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3438-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3438-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3438-119">See Also</span></span>  
 [<span data-ttu-id="c3438-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="c3438-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
