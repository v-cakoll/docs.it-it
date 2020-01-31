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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867023"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="8af34-102">Enumerazione COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="8af34-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="8af34-103">Specifica la quantità di dati da passare di nuovo con uno snapshot dello stack in ogni chiamata alla funzione [StackSnapshotCallback](stacksnapshotcallback-function.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="8af34-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8af34-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="8af34-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8af34-105">Members</span></span>  
  
|<span data-ttu-id="8af34-106">Membri</span><span class="sxs-lookup"><span data-stu-id="8af34-106">Members</span></span>|<span data-ttu-id="8af34-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8af34-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="8af34-108">Indica che i valori devono essere passati per tutti i parametri di `StackSnapshotCallback`, ad eccezione del parametro `context`.</span><span class="sxs-lookup"><span data-stu-id="8af34-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="8af34-109">Indica che i valori devono essere passati per tutti i parametri di `StackSnapshotCallback`, incluso il parametro `context`.</span><span class="sxs-lookup"><span data-stu-id="8af34-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="8af34-110">Indica che verrà utilizzato un algoritmo più semplice e alternativo per lo stack.</span><span class="sxs-lookup"><span data-stu-id="8af34-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af34-111">Note</span><span class="sxs-lookup"><span data-stu-id="8af34-111">Remarks</span></span>  
 <span data-ttu-id="8af34-112">I valori forniti dall'enumerazione `COR_PRF_SNAPSHOT_INFO` vengono passati come parametri al metodo [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8af34-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af34-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8af34-113">Requirements</span></span>  
 <span data-ttu-id="8af34-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af34-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8af34-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8af34-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8af34-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8af34-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af34-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8af34-118">See also</span></span>

- [<span data-ttu-id="8af34-119">Metodo DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="8af34-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="8af34-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="8af34-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
