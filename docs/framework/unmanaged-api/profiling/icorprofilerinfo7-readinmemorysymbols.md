---
title: 'ICorProfilerInfo7:: ReadInMemorySymbols'
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
ms.openlocfilehash: 6732457220d795bbf8ae54277ef9f5c07cf96359
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495359"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="a71cc-102">ICorProfilerInfo7:: ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="a71cc-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="a71cc-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="a71cc-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="a71cc-104">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="a71cc-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71cc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a71cc-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a71cc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a71cc-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a71cc-107">in Identificatore del modulo contenente il flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="a71cc-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="a71cc-108">in Offset all'interno del flusso in memoria da cui iniziare la lettura dei byte.</span><span class="sxs-lookup"><span data-stu-id="a71cc-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="a71cc-109">out Puntatore al buffer in cui verranno copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="a71cc-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="a71cc-110">Lo spazio del buffer deve essere `countSymbolBytes` disponibile.</span><span class="sxs-lookup"><span data-stu-id="a71cc-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="a71cc-111">in Numero di byte da copiare.</span><span class="sxs-lookup"><span data-stu-id="a71cc-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="a71cc-112">out Quando il metodo viene restituito, contiene il numero effettivo di byte letti.</span><span class="sxs-lookup"><span data-stu-id="a71cc-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a71cc-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a71cc-113">Return Value</span></span>  
 <span data-ttu-id="a71cc-114">`S_OK`Se è stato letto un numero di byte diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="a71cc-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="a71cc-115">`CORPROF_E_MODULE_IS_DYNAMIC`Se il modulo è stato creato usando <xref:System.Reflection.Emit> .</span><span class="sxs-lookup"><span data-stu-id="a71cc-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a71cc-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a71cc-116">Remarks</span></span>  
 <span data-ttu-id="a71cc-117">Il `ReadInMemorySymbols` metodo tenta di leggere i `countSymbolBytes` dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="a71cc-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="a71cc-118">I dati vengono copiati in `pSymbolBytes` , che dovrebbe avere `countSymbolBytes` spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="a71cc-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="a71cc-119">`pCountSymbolsBytesRead`contiene il numero effettivo di byte letti, che può essere minore di `countSymbolBytes` se viene raggiunta la fine del flusso.</span><span class="sxs-lookup"><span data-stu-id="a71cc-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a71cc-120">L'implementazione corrente non supporta Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="a71cc-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="a71cc-121">Se il modulo è stato creato usando Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="a71cc-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a71cc-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a71cc-122">Requirements</span></span>  
 <span data-ttu-id="a71cc-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a71cc-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a71cc-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a71cc-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a71cc-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a71cc-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a71cc-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a71cc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a71cc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a71cc-127">See also</span></span>

- [<span data-ttu-id="a71cc-128">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="a71cc-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
