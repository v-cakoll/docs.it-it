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
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868343"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="786dc-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="786dc-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="786dc-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="786dc-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="786dc-104">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="786dc-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="786dc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="786dc-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="786dc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="786dc-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="786dc-107">in Identificatore del modulo contenente il flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="786dc-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="786dc-108">in Offset all'interno del flusso in memoria da cui iniziare la lettura dei byte.</span><span class="sxs-lookup"><span data-stu-id="786dc-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="786dc-109">out Puntatore al buffer in cui verranno copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="786dc-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="786dc-110">Il buffer deve avere `countSymbolBytes` dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="786dc-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="786dc-111">in Numero di byte da copiare.</span><span class="sxs-lookup"><span data-stu-id="786dc-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="786dc-112">out Quando il metodo viene restituito, contiene il numero effettivo di byte letti.</span><span class="sxs-lookup"><span data-stu-id="786dc-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="786dc-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="786dc-113">Return Value</span></span>  
 <span data-ttu-id="786dc-114">`S_OK`se è stato letto un numero di byte diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="786dc-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="786dc-115">`CORPROF_E_MODULE_IS_DYNAMIC`, se il modulo è stato creato con <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="786dc-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="786dc-116">Note</span><span class="sxs-lookup"><span data-stu-id="786dc-116">Remarks</span></span>  
 <span data-ttu-id="786dc-117">Il metodo `ReadInMemorySymbols` tenta di leggere `countSymbolBytes` di dati a partire dall'offset `symbolsReadOffset` all'interno del flusso in memoria.</span><span class="sxs-lookup"><span data-stu-id="786dc-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="786dc-118">I dati vengono copiati in `pSymbolBytes`, che dovrebbe avere `countSymbolBytes` di spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="786dc-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="786dc-119">`pCountSymbolsBytesRead` contiene il numero effettivo di byte letti, che può essere minore di `countSymbolBytes` se viene raggiunta la fine del flusso.</span><span class="sxs-lookup"><span data-stu-id="786dc-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="786dc-120">L'implementazione corrente non supporta Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="786dc-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="786dc-121">Se il modulo è stato creato usando Reflection. Emit, il metodo restituisce `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="786dc-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="786dc-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="786dc-122">Requirements</span></span>  
 <span data-ttu-id="786dc-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="786dc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="786dc-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="786dc-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="786dc-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="786dc-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="786dc-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="786dc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786dc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="786dc-127">See also</span></span>

- [<span data-ttu-id="786dc-128">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="786dc-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
