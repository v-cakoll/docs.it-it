---
title: Metodo ICorProfilerInfo::GetObjectSize
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42e86b1eac788b709432d39e320ebea49c696c14
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481704"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="99ca0-102">Metodo ICorProfilerInfo::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="99ca0-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="99ca0-103">Ottiene le dimensioni di un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="99ca0-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ca0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99ca0-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99ca0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99ca0-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="99ca0-106">[in] L'ID dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="99ca0-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="99ca0-107">[out] Puntatore alla dimensione dell'oggetto, in byte.</span><span class="sxs-lookup"><span data-stu-id="99ca0-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99ca0-108">Note</span><span class="sxs-lookup"><span data-stu-id="99ca0-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="99ca0-109">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="99ca0-109">This method is obsolete.</span></span> <span data-ttu-id="99ca0-110">Restituisce COR_E_OVERFLOW per gli oggetti maggiori di 4GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="99ca0-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="99ca0-111">Usare la [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="99ca0-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="99ca0-112">Oggetti diversi dello stesso tipo sono spesso le stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="99ca0-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="99ca0-113">Tuttavia, alcuni tipi, ad esempio le matrici o stringhe, potrebbero essere una dimensione diversa per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="99ca0-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="99ca0-114">Le dimensioni restituite dal `GetObjectSize` (metodo) non include eventuali spaziature interne di allineamento che possono essere visualizzati dopo che l'oggetto è nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="99ca0-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="99ca0-115">Se si usa il `GetObjectSize` metodo per passare da un oggetto a un oggetto nell'heap di garbage collection, aggiungere padding manualmente, in base alle esigenze di allineamento.</span><span class="sxs-lookup"><span data-stu-id="99ca0-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
-   <span data-ttu-id="99ca0-116">In Windows a 32 bit, COR_PRF_GC_GEN_0 COR_PRF_GC_GEN_1 e COR_PRF_GC_GEN_2 usano l'allineamento a 4 byte e COR_PRF_GC_LARGE_OBJECT_HEAP Usa l'allineamento a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="99ca0-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
-   <span data-ttu-id="99ca0-117">In Windows a 64 bit, l'allineamento è sempre 8 byte.</span><span class="sxs-lookup"><span data-stu-id="99ca0-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ca0-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99ca0-118">Requirements</span></span>  
 <span data-ttu-id="99ca0-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ca0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ca0-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99ca0-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99ca0-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99ca0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99ca0-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ca0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ca0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99ca0-123">See also</span></span>
- [<span data-ttu-id="99ca0-124">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="99ca0-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
