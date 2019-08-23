---
title: 'Metodo ICorProfilerInfo7:: GetInMemorySymbolsLength'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955418"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="00444-102">Metodo ICorProfilerInfo7:: GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="00444-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="00444-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="00444-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="00444-104">Restituisce la lunghezza di un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="00444-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00444-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00444-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00444-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="00444-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="00444-107">in Identificatore del modulo contenente il flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="00444-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="00444-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="00444-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="00444-109">out Puntatore a un `DWORD` valore che, quando il metodo viene restituito, contiene la lunghezza del flusso in byte.</span><span class="sxs-lookup"><span data-stu-id="00444-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00444-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00444-110">Return Value</span></span>  
 <span data-ttu-id="00444-111">Il metodo restituisce `S_OK` se è possibile determinare la lunghezza del flusso di memoria, anche se è zero (0).</span><span class="sxs-lookup"><span data-stu-id="00444-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="00444-112">Il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC` se il metodo è stato creato <xref:System.Reflection.Emit?displayProperty=nameWithType>utilizzando.</span><span class="sxs-lookup"><span data-stu-id="00444-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00444-113">Note</span><span class="sxs-lookup"><span data-stu-id="00444-113">Remarks</span></span>  
 <span data-ttu-id="00444-114">Se il modulo dispone di simboli in memoria, la lunghezza del flusso viene posizionata in `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="00444-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="00444-115">Se il modulo non dispone di simboli in memoria, `*pCountSymbolBytes = 0`.</span><span class="sxs-lookup"><span data-stu-id="00444-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00444-116">L'implementazione corrente non supporta Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="00444-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="00444-117">Se il modulo è stato creato usando Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="00444-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00444-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00444-118">Requirements</span></span>  
 <span data-ttu-id="00444-119">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00444-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00444-120">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="00444-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00444-121">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00444-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00444-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00444-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00444-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00444-123">See also</span></span>

- [<span data-ttu-id="00444-124">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="00444-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
