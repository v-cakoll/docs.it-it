---
title: Metodo ICorDebugILFrame3::GetReturnValueForILOffset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5832ec095ea0e96327f6a9636193da9c0c8a5dd2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988271"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="03f3f-102">Metodo ICorDebugILFrame3::GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="03f3f-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="03f3f-103">Ottiene un oggetto "ICorDebugValue" che incapsula il valore restituito di una funzione.</span><span class="sxs-lookup"><span data-stu-id="03f3f-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03f3f-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03f3f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03f3f-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="03f3f-106">Offset IL.</span><span class="sxs-lookup"><span data-stu-id="03f3f-106">The IL offset.</span></span> <span data-ttu-id="03f3f-107">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="03f3f-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="03f3f-108">Puntatore all'indirizzo di un oggetto interfaccia "ICorDebugValue" che fornisce informazioni sul valore restituito di una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="03f3f-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03f3f-109">Note</span><span class="sxs-lookup"><span data-stu-id="03f3f-109">Remarks</span></span>  
 <span data-ttu-id="03f3f-110">Questo metodo viene usato insieme al metodo [ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) per ottenere il valore restituito di un metodo.</span><span class="sxs-lookup"><span data-stu-id="03f3f-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="03f3f-111">È particolarmente utile nel caso di metodi i cui valori restituiti vengono ignorati, come nei due esempi di codice seguenti.</span><span class="sxs-lookup"><span data-stu-id="03f3f-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="03f3f-112">Nel primo esempio viene chiamato <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> il metodo, ma viene ignorato il valore restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="03f3f-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="03f3f-113">Nel secondo esempio viene illustrato un problema molto più comune nel debug.</span><span class="sxs-lookup"><span data-stu-id="03f3f-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="03f3f-114">Poiché un metodo viene usato come argomento in una chiamata al metodo, il relativo valore restituito è accessibile solo quando il debugger passa attraverso il metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="03f3f-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="03f3f-115">In molti casi, in particolare quando il metodo chiamato viene definito in una libreria esterna, non è possibile.</span><span class="sxs-lookup"><span data-stu-id="03f3f-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="03f3f-116">Se si passa il metodo [ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) un offset il a un sito di chiamata di funzione, viene restituito uno o più offset nativi.</span><span class="sxs-lookup"><span data-stu-id="03f3f-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="03f3f-117">Il debugger può quindi impostare punti di interruzione su questi offset nativi nella funzione.</span><span class="sxs-lookup"><span data-stu-id="03f3f-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="03f3f-118">Quando il debugger raggiunge uno dei punti di interruzione, è possibile passare lo stesso offset IL passato a questo metodo per ottenere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="03f3f-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="03f3f-119">Il debugger dovrebbe quindi cancellare tutti i punti di interruzione impostati.</span><span class="sxs-lookup"><span data-stu-id="03f3f-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="03f3f-120">Il [Metodo ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) e `ICorDebugILFrame3::GetReturnValueForILOffset` i metodi consentono di ottenere informazioni sul valore restituito solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="03f3f-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="03f3f-121">Il recupero delle informazioni sul valore restituito dai tipi di valore (ovvero tutti i tipi che derivano da <xref:System.ValueType>) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="03f3f-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="03f3f-122">L'offset il specificato dal `ILOffset` parametro deve trovarsi in un sito di chiamata di funzione e l'oggetto del debug deve essere interrotto in corrispondenza di un punto di interruzione impostato in corrispondenza dell'offset nativo restituito dal metodo [ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) per lo stesso offset il.</span><span class="sxs-lookup"><span data-stu-id="03f3f-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="03f3f-123">Se l'oggetto del debug non viene arrestato nella posizione corretta per l'offset IL specificato, l'API avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="03f3f-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="03f3f-124">Se la chiamata di funzione non restituisce un valore, l'API avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="03f3f-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="03f3f-125">Il `ICorDebugILFrame3::GetReturnValueForILOffset` metodo è disponibile solo nei sistemi basati su x86 e amd64.</span><span class="sxs-lookup"><span data-stu-id="03f3f-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03f3f-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03f3f-126">Requirements</span></span>  
 <span data-ttu-id="03f3f-127">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03f3f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f3f-128">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="03f3f-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03f3f-129">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03f3f-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03f3f-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03f3f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f3f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03f3f-131">See also</span></span>

- [<span data-ttu-id="03f3f-132">Metodo GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="03f3f-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="03f3f-133">Interfaccia ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="03f3f-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
