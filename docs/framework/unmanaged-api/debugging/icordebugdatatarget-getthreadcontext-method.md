---
title: Metodo ICorDebugDataTarget::GetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 543956bb42d7477456426d7327f14b059b23d759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="a6439-102">Metodo ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="a6439-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="a6439-103">Restituisce il contesto del thread corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="a6439-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6439-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6439-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6439-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6439-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="a6439-106">[in] L'identificatore del thread il cui contesto è da recuperare.</span><span class="sxs-lookup"><span data-stu-id="a6439-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="a6439-107">L'identificatore è definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6439-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="a6439-108">[in] Combinazione bit per bit di flag dipendente dalla piattaforma che indicano quali parti del contesto deve essere letti.</span><span class="sxs-lookup"><span data-stu-id="a6439-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a6439-109">[in] Le dimensioni di `pContext`.</span><span class="sxs-lookup"><span data-stu-id="a6439-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="a6439-110">[out] Buffer in cui verrà archiviato nel contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="a6439-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6439-111">Note</span><span class="sxs-lookup"><span data-stu-id="a6439-111">Remarks</span></span>  
 <span data-ttu-id="a6439-112">Su piattaforme Windows, `pContext` deve essere un `CONTEXT` struttura (definito in Winnt. H) appropriata per il tipo di computer specificato per il [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="a6439-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="a6439-113">`contextFlags`deve avere gli stessi valori di `ContextFlags` campo il `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="a6439-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="a6439-114">Il `CONTEXT` struttura è specifico del processore, vedere il file Winnt. H per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="a6439-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6439-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6439-115">Requirements</span></span>  
 <span data-ttu-id="a6439-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6439-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6439-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a6439-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6439-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6439-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6439-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6439-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6439-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6439-120">See Also</span></span>  
 [<span data-ttu-id="a6439-121">ICorDebugDataTarget (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a6439-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="a6439-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a6439-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a6439-123">Debug</span><span class="sxs-lookup"><span data-stu-id="a6439-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
