---
title: Metodo ICorDebugCode3::GetReturnValueLiveOffset
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: dc03365b72a5f3613402faf1aed44b5683e9892c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777829"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="3a4ce-102">Metodo ICorDebugCode3::GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="3a4ce-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="3a4ce-103">Per un offset IL specificato, ottiene gli offset nativi in cui deve essere inserito un punto di interruzione in modo che il debugger possa ottenere il valore restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a4ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a4ce-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a4ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a4ce-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="3a4ce-106">Offset IL.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-106">The IL offset.</span></span> <span data-ttu-id="3a4ce-107">Deve essere un sito di chiamata di funzione o la chiamata di funzione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="3a4ce-108">Numero di byte disponibili per l'archiviazione `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="3a4ce-109">Puntatore al numero di offset effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="3a4ce-110">In genere, il valore è 1, ma una singola istruzione IL può eseguire il mapping a più istruzioni di assembly `CALL`.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="3a4ce-111">Matrice di offset nativi.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-111">An array of native offsets.</span></span> <span data-ttu-id="3a4ce-112">In genere, `pOffsets` contiene un solo offset, sebbene sia possibile eseguire il mapping di una singola istruzione IL a più mapping a più istruzioni di `CALL` assembly.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a4ce-113">Note</span><span class="sxs-lookup"><span data-stu-id="3a4ce-113">Remarks</span></span>  
 <span data-ttu-id="3a4ce-114">Questo metodo viene usato insieme al metodo [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) per ottenere il valore restituito di un metodo che restituisce un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="3a4ce-115">Il passaggio di un offset IL a un sito di chiamata di funzione a questo metodo restituisce uno o più offset nativi.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="3a4ce-116">Il debugger può quindi impostare punti di interruzione su questi offset nativi nella funzione.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="3a4ce-117">Quando il debugger raggiunge uno dei punti di interruzione, è possibile passare lo stesso offset IL passato a questo metodo al metodo [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) per ottenere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="3a4ce-118">Il debugger dovrebbe quindi cancellare tutti i punti di interruzione impostati.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="3a4ce-119">I metodi `ICorDebugCode3::GetReturnValueLiveOffset` e [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) consentono di ottenere informazioni sul valore restituito solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="3a4ce-120">Il recupero delle informazioni sul valore restituito dai tipi valore, ovvero tutti i tipi che derivano da <xref:System.ValueType>, non è supportato.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="3a4ce-121">La funzione restituisce i valori `HRESULT` illustrati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="3a4ce-122">Valore di `HRESULT`</span><span class="sxs-lookup"><span data-stu-id="3a4ce-122">`HRESULT` value</span></span>|<span data-ttu-id="3a4ce-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a4ce-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="3a4ce-124">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="3a4ce-125">Il sito di offset IL specificato non è un'istruzione di chiamata o la funzione restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="3a4ce-126">L'offset IL specificato è una chiamata corretta, ma il tipo restituito non è supportato per ottenere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="3a4ce-127">Il metodo `ICorDebugCode3::GetReturnValueLiveOffset` è disponibile solo nei sistemi AMD64 e x86.</span><span class="sxs-lookup"><span data-stu-id="3a4ce-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a4ce-128">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3a4ce-128">Requirements</span></span>  
 <span data-ttu-id="3a4ce-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a4ce-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a4ce-130">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a4ce-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a4ce-131">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a4ce-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a4ce-132">**Versioni .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a4ce-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4ce-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a4ce-133">See also</span></span>

- [<span data-ttu-id="3a4ce-134">Metodo GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="3a4ce-134">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="3a4ce-135">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="3a4ce-135">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
