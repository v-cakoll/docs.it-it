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
ms.openlocfilehash: 6168c5b27868a261871b292e17ca02b04ae89917
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500780"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="17a15-102">Enumerazione COR_PRF_SNAPSHOT_INFO</span><span class="sxs-lookup"><span data-stu-id="17a15-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="17a15-103">Specifica la quantità di dati da passare di nuovo con uno snapshot dello stack in ogni chiamata alla funzione [StackSnapshotCallback](stacksnapshotcallback-function.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="17a15-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17a15-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="17a15-105">Membri</span><span class="sxs-lookup"><span data-stu-id="17a15-105">Members</span></span>  
  
|<span data-ttu-id="17a15-106">Membri</span><span class="sxs-lookup"><span data-stu-id="17a15-106">Members</span></span>|<span data-ttu-id="17a15-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17a15-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="17a15-108">Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, ad eccezione del `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="17a15-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="17a15-109">Indica che i valori devono essere passati per tutti i `StackSnapshotCallback` parametri, incluso il `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="17a15-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="17a15-110">Indica che verrà utilizzato un algoritmo più semplice e alternativo per lo stack.</span><span class="sxs-lookup"><span data-stu-id="17a15-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17a15-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="17a15-111">Remarks</span></span>  
 <span data-ttu-id="17a15-112">I valori forniti dall' `COR_PRF_SNAPSHOT_INFO` enumerazione vengono passati come parametri al metodo [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="17a15-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17a15-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17a15-113">Requirements</span></span>  
 <span data-ttu-id="17a15-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17a15-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17a15-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17a15-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17a15-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17a15-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17a15-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17a15-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a15-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17a15-118">See also</span></span>

- [<span data-ttu-id="17a15-119">Metodo DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="17a15-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="17a15-120">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="17a15-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
