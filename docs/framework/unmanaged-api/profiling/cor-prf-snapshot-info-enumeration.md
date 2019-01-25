---
title: Enumerazione COR_PRF_SNAPSHOT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33c233f2699c89e5acfb0fda13f74589f1c5dd4b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741600"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="62f54-102">Enumerazione COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="62f54-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="62f54-103">Specifica quanto nuovamente i dati da passare con uno snapshot dello stack in ogni chiamata a del profiler [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="62f54-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62f54-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="62f54-105">Membri</span><span class="sxs-lookup"><span data-stu-id="62f54-105">Members</span></span>  
  
|<span data-ttu-id="62f54-106">Membri</span><span class="sxs-lookup"><span data-stu-id="62f54-106">Members</span></span>|<span data-ttu-id="62f54-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62f54-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="62f54-108">Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, ad eccezione di `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="62f54-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="62f54-109">Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, incluso il `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="62f54-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="62f54-110">Indica che verrà utilizzato un algoritmo di analisi dello stack più semplice, alternativo.</span><span class="sxs-lookup"><span data-stu-id="62f54-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62f54-111">Note</span><span class="sxs-lookup"><span data-stu-id="62f54-111">Remarks</span></span>  
 <span data-ttu-id="62f54-112">Valori forniti per il `COR_PRF_SNAPSHOT_INFO` enumerazione vengono passati come parametri per il [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="62f54-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f54-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62f54-113">Requirements</span></span>  
 <span data-ttu-id="62f54-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62f54-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f54-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62f54-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62f54-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62f54-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62f54-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62f54-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f54-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f54-118">See also</span></span>
- [<span data-ttu-id="62f54-119">Metodo DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="62f54-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="62f54-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="62f54-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
