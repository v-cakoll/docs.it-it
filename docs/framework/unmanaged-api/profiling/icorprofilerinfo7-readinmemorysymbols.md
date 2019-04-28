---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786209"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="18302-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="18302-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="18302-103">[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="18302-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="18302-104">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="18302-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18302-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18302-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18302-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="18302-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="18302-107">[in] L'identificatore del modulo contenente il flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="18302-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="18302-108">[in] L'offset all'interno del flusso in memoria in corrispondenza del quale iniziare la lettura dei byte.</span><span class="sxs-lookup"><span data-stu-id="18302-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="18302-109">[out] Un puntatore al buffer in cui verranno copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="18302-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="18302-110">Il buffer deve avere `countSymbolBytes` di spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="18302-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="18302-111">[in] Il numero di byte da copiare.</span><span class="sxs-lookup"><span data-stu-id="18302-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="18302-112">[out] Quando il metodo viene restituito, contiene il numero effettivo di byte letti.</span><span class="sxs-lookup"><span data-stu-id="18302-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18302-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="18302-113">Return Value</span></span>  
 <span data-ttu-id="18302-114">`S_OK`, se un numero diverso da zero di byte letti.</span><span class="sxs-lookup"><span data-stu-id="18302-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="18302-115">`CORPROF_E_MODULE_IS_DYNAMIC`, se il modulo è stato creato usando <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="18302-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18302-116">Note</span><span class="sxs-lookup"><span data-stu-id="18302-116">Remarks</span></span>  
 <span data-ttu-id="18302-117">Il `ReadInMemorySymbols` metodo tenta di leggere `countSymbolBytes` dei dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="18302-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="18302-118">I dati vengono copiati `pSymbolBytes`, che deve disporre di `countSymbolBytes` dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="18302-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="18302-119">`pCountSymbolsBytesRead` contiene il numero effettivo di byte letti, che può essere inferiore rispetto a `countSymbolBytes` se viene raggiunta la fine del flusso.</span><span class="sxs-lookup"><span data-stu-id="18302-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18302-120">L'implementazione corrente non supporta Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="18302-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="18302-121">Se il modulo è stato creato tramite Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="18302-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18302-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18302-122">Requirements</span></span>  
 <span data-ttu-id="18302-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18302-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18302-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18302-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18302-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18302-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18302-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18302-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18302-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18302-127">See also</span></span>

- [<span data-ttu-id="18302-128">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="18302-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
