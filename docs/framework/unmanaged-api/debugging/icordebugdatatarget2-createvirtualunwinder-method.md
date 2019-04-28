---
title: Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c8befed8bc810344b2a3344212a6a4a854300e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763822"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="49662-102">Metodo ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="49662-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="49662-103">Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).</span><span class="sxs-lookup"><span data-stu-id="49662-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49662-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49662-104">Syntax</span></span>  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="49662-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49662-105">Parameters</span></span>  
 <span data-ttu-id="49662-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="49662-106">nativeThreadID</span></span>  
 <span data-ttu-id="49662-107">[in] L'ID thread nativo del thread di cui rimuovere lo stack.</span><span class="sxs-lookup"><span data-stu-id="49662-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="49662-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="49662-108">contextFlags</span></span>  
 <span data-ttu-id="49662-109">[in] Flag che specificano le parti del contesto definite in `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="49662-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="49662-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="49662-110">cbContext</span></span>  
 <span data-ttu-id="49662-111">[in] Le dimensioni di `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="49662-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="49662-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="49662-112">initialContext</span></span>  
 <span data-ttu-id="49662-113">[in] I dati nel contesto.</span><span class="sxs-lookup"><span data-stu-id="49662-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="49662-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="49662-114">ppUnwinder</span></span>  
 <span data-ttu-id="49662-115">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="49662-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49662-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="49662-116">Return Value</span></span>  
 <span data-ttu-id="49662-117">`S_OK` se l'operazione riesce.</span><span class="sxs-lookup"><span data-stu-id="49662-117">`S_OK` if successful.</span></span> <span data-ttu-id="49662-118">Qualsiasi altro `HRESULT` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="49662-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="49662-119">Qualsiasi errore `HRESULT` ricevuto da mscordbi viene considerato irreversibile e causa [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) metodi di restituire `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="49662-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49662-120">Note</span><span class="sxs-lookup"><span data-stu-id="49662-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49662-121">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="49662-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49662-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49662-122">Requirements</span></span>  
 <span data-ttu-id="49662-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49662-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49662-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49662-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49662-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49662-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49662-126">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49662-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49662-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49662-127">See also</span></span>

- [<span data-ttu-id="49662-128">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="49662-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="49662-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="49662-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
