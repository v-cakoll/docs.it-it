---
title: 'Icorprofilerinfo7:: Readinmemorysymbols'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5851f73cc899ef21d8a5dcfd8f03617641a6625a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="6c2c7-102">Icorprofilerinfo7:: Readinmemorysymbols</span><span class="sxs-lookup"><span data-stu-id="6c2c7-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="6c2c7-103">[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="6c2c7-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="6c2c7-104">Legge i byte dal flusso simbolo in memoria.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c2c7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c2c7-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c2c7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c2c7-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="6c2c7-107">[in] L'identificatore del modulo contenente il flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="6c2c7-108">[in] L'offset all'interno del flusso in memoria in corrispondenza del quale iniziare la lettura dei byte.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="6c2c7-109">[out] Un puntatore al buffer in cui verranno copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="6c2c7-110">Il buffer deve essere `countSymbolBytes` di spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="6c2c7-111">[in] Il numero di byte da copiare.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="6c2c7-112">[out] Quando il metodo viene restituito, contiene il numero effettivo di byte letti.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c2c7-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c2c7-113">Return Value</span></span>  
 <span data-ttu-id="6c2c7-114">`S_OK`, se un numero diverso da zero di byte letti.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="6c2c7-115">`CORPROF_E_MODULE_IS_DYNAMIC`, se il modulo è stato creato utilizzando <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c2c7-116">Note</span><span class="sxs-lookup"><span data-stu-id="6c2c7-116">Remarks</span></span>  
 <span data-ttu-id="6c2c7-117">Il `ReadInMemorySymbols` metodo tenta di leggere `countSymbolBytes` dei dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="6c2c7-118">I dati vengono copiati in `pSymbolBytes`, che dovranno avere `countSymbolBytes` di spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="6c2c7-119">`pCountSymbolsBytesRead`contiene il numero effettivo di byte letti, che può essere inferiore rispetto a `countSymbolBytes` se viene raggiunta la fine del flusso.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c2c7-120">L'implementazione corrente non supporta Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="6c2c7-121">Se il modulo è stato creato tramite Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="6c2c7-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c2c7-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c2c7-122">Requirements</span></span>  
 <span data-ttu-id="6c2c7-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c2c7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c2c7-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c2c7-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c2c7-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c2c7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c2c7-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c2c7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2c7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c2c7-127">See Also</span></span>  
 [<span data-ttu-id="6c2c7-128">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="6c2c7-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
