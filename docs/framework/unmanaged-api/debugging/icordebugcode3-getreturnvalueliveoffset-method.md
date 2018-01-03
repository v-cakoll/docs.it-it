---
title: Metodo ICorDebugCode3::GetReturnValueLiveOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d10d298a031e7146eaf6cf7988538e6f7020136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="3faee-102">Metodo ICorDebugCode3::GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="3faee-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="3faee-103">Per un offset IL specificato, ottiene gli offset nativi in un punto di interruzione deve essere posizionato in modo che il debugger è possibile ottenere il valore restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="3faee-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3faee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3faee-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3faee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3faee-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="3faee-106">Offset IL.</span><span class="sxs-lookup"><span data-stu-id="3faee-106">The IL offset.</span></span> <span data-ttu-id="3faee-107">Deve essere un sito di chiamata di funzione o la chiamata di funzione non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="3faee-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="3faee-108">Il numero di byte disponibili per archiviare `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="3faee-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="3faee-109">Puntatore al numero di offset effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="3faee-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="3faee-110">In genere, il relativo valore è 1, ma è possibile eseguire il mapping di una singola istruzione IL multiplo `CALL` le istruzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="3faee-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="3faee-111">Matrice di offset nativi.</span><span class="sxs-lookup"><span data-stu-id="3faee-111">An array of native offsets.</span></span> <span data-ttu-id="3faee-112">In genere, `pOffsets` contiene solo un offset, anche se è possibile eseguire il mapping di una singola istruzione di linguaggio intermedio con mapping più in più `CALL` le istruzioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="3faee-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3faee-113">Note</span><span class="sxs-lookup"><span data-stu-id="3faee-113">Remarks</span></span>  
 <span data-ttu-id="3faee-114">Questo metodo viene utilizzato insieme al [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito di un metodo che restituisce un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3faee-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="3faee-115">Il passaggio di un offset a un sito di chiamata di funzione per questo metodo IL restituisce uno o più offset nativi.</span><span class="sxs-lookup"><span data-stu-id="3faee-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="3faee-116">Il debugger può quindi impostare i punti di interruzione in questi offset nativi nella funzione.</span><span class="sxs-lookup"><span data-stu-id="3faee-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="3faee-117">Quando il debugger raggiunge uno dei punti di interruzione, è quindi possibile passare lo stesso offset IL che è stato passato a questo metodo per il [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3faee-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="3faee-118">Il debugger deve quindi deselezionare tutti i punti di interruzione è impostato.</span><span class="sxs-lookup"><span data-stu-id="3faee-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3faee-119">Il `ICorDebugCode3::GetReturnValueLiveOffset` e [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodi consentono di ottenere informazioni sul valore restituito per solo i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3faee-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="3faee-120">Recupero delle informazioni di valore restituito da tipi di valore (vale a dire tutti i tipi che derivano da <xref:System.ValueType>) non è supportata.</span><span class="sxs-lookup"><span data-stu-id="3faee-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="3faee-121">La funzione restituisce il `HRESULT` sui valori indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3faee-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="3faee-122">Valore di `HRESULT`</span><span class="sxs-lookup"><span data-stu-id="3faee-122">`HRESULT` value</span></span>|<span data-ttu-id="3faee-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3faee-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="3faee-124">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="3faee-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="3faee-125">Il sito di offset IL specificato non è un'istruzione di chiamata o la funzione restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="3faee-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="3faee-126">L'offset IL specificato è una chiamata corretta, ma il tipo restituito non è supportato per il recupero di un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3faee-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="3faee-127">Il `ICorDebugCode3::GetReturnValueLiveOffset` metodo è disponibile solo nel server basato su x86 e sistemi AMD64.</span><span class="sxs-lookup"><span data-stu-id="3faee-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3faee-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3faee-128">Requirements</span></span>  
 <span data-ttu-id="3faee-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3faee-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3faee-130">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3faee-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3faee-131">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3faee-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3faee-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3faee-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3faee-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3faee-133">See Also</span></span>  
 [<span data-ttu-id="3faee-134">Metodo GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="3faee-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="3faee-135">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="3faee-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
