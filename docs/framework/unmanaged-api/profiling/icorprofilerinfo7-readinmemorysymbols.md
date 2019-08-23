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
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955366"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="114f6-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="114f6-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="114f6-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="114f6-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="114f6-104">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="114f6-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114f6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="114f6-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="114f6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="114f6-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="114f6-107">in Identificatore del modulo contenente il flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="114f6-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="114f6-108">in Offset all'interno del flusso in memoria da cui iniziare la lettura dei byte.</span><span class="sxs-lookup"><span data-stu-id="114f6-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="114f6-109">out Puntatore al buffer in cui verranno copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="114f6-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="114f6-110">Lo spazio del buffer `countSymbolBytes` deve essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="114f6-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="114f6-111">in Numero di byte da copiare.</span><span class="sxs-lookup"><span data-stu-id="114f6-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="114f6-112">out Quando il metodo viene restituito, contiene il numero effettivo di byte letti.</span><span class="sxs-lookup"><span data-stu-id="114f6-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="114f6-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="114f6-113">Return Value</span></span>  
 <span data-ttu-id="114f6-114">`S_OK`Se è stato letto un numero di byte diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="114f6-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="114f6-115">`CORPROF_E_MODULE_IS_DYNAMIC`Se il modulo è stato creato usando <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="114f6-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="114f6-116">Note</span><span class="sxs-lookup"><span data-stu-id="114f6-116">Remarks</span></span>  
 <span data-ttu-id="114f6-117">Il `ReadInMemorySymbols` metodo tenta di leggere `countSymbolBytes` i dati a partire dall' `symbolsReadOffset` offset all'interno del flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="114f6-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="114f6-118">I dati vengono copiati `pSymbolBytes`in, che dovrebbe avere `countSymbolBytes` spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="114f6-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="114f6-119">`pCountSymbolsBytesRead`contiene il numero effettivo di byte letti, che può essere minore di `countSymbolBytes` se viene raggiunta la fine del flusso.</span><span class="sxs-lookup"><span data-stu-id="114f6-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="114f6-120">L'implementazione corrente non supporta Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="114f6-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="114f6-121">Se il modulo è stato creato usando Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="114f6-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="114f6-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="114f6-122">Requirements</span></span>  
 <span data-ttu-id="114f6-123">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="114f6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114f6-124">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="114f6-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="114f6-125">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="114f6-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="114f6-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="114f6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114f6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="114f6-127">See also</span></span>

- [<span data-ttu-id="114f6-128">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="114f6-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
