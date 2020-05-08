---
title: Metodo ICorDebugDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 79708aa5a2abcb8d7465f82a8beb918484c193b9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976551"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="e1810-102">Metodo ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="e1810-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="e1810-103">Restituisce il contesto del thread corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="e1810-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1810-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1810-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1810-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1810-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="e1810-106">in Identificatore del thread di cui è necessario recuperare il contesto.</span><span class="sxs-lookup"><span data-stu-id="e1810-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="e1810-107">L'identificatore viene definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e1810-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="e1810-108">in Combinazione bit per bit di flag dipendenti dalla piattaforma che indicano quali parti del contesto devono essere lette.</span><span class="sxs-lookup"><span data-stu-id="e1810-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e1810-109">[in] Le dimensioni di `pContext`.</span><span class="sxs-lookup"><span data-stu-id="e1810-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="e1810-110">out Buffer in cui verrà archiviato il contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="e1810-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1810-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e1810-111">Remarks</span></span>  
 <span data-ttu-id="e1810-112">Nelle piattaforme Windows, `pContext` deve essere una `CONTEXT` struttura (definita in Winnt. h) appropriata per il tipo di computer specificato dal metodo [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e1810-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="e1810-113">`contextFlags`deve avere gli stessi valori del `ContextFlags` campo della `CONTEXT` struttura.</span><span class="sxs-lookup"><span data-stu-id="e1810-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="e1810-114">La `CONTEXT` struttura è specifica del processore. per informazioni dettagliate, vedere il file WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="e1810-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1810-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1810-115">Requirements</span></span>  
 <span data-ttu-id="e1810-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1810-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1810-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1810-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1810-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1810-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1810-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1810-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1810-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1810-120">See also</span></span>

- [<span data-ttu-id="e1810-121">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="e1810-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="e1810-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e1810-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e1810-123">Debug</span><span class="sxs-lookup"><span data-stu-id="e1810-123">Debugging</span></span>](index.md)
