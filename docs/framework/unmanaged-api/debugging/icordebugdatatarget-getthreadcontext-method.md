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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783722"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="23b3f-102">Metodo ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="23b3f-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="23b3f-103">Restituisce il contesto del thread corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="23b3f-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23b3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23b3f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23b3f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23b3f-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="23b3f-106">in Identificatore del thread di cui è necessario recuperare il contesto.</span><span class="sxs-lookup"><span data-stu-id="23b3f-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="23b3f-107">L'identificatore viene definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="23b3f-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="23b3f-108">in Combinazione bit per bit di flag dipendenti dalla piattaforma che indicano quali parti del contesto devono essere lette.</span><span class="sxs-lookup"><span data-stu-id="23b3f-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="23b3f-109">[in] Le dimensioni di `pContext`.</span><span class="sxs-lookup"><span data-stu-id="23b3f-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="23b3f-110">out Buffer in cui verrà archiviato il contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="23b3f-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23b3f-111">Note</span><span class="sxs-lookup"><span data-stu-id="23b3f-111">Remarks</span></span>  
 <span data-ttu-id="23b3f-112">Nelle piattaforme Windows, `pContext` deve essere una struttura di `CONTEXT` (definita in WinNT. h) appropriata per il tipo di computer specificato dal metodo [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="23b3f-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="23b3f-113">`contextFlags` deve avere gli stessi valori del campo `ContextFlags` della struttura `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="23b3f-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="23b3f-114">La struttura di `CONTEXT` è specifica del processore. per informazioni dettagliate, vedere il file WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="23b3f-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23b3f-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="23b3f-115">Requirements</span></span>  
 <span data-ttu-id="23b3f-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23b3f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23b3f-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23b3f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23b3f-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23b3f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23b3f-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23b3f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b3f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b3f-120">See also</span></span>

- [<span data-ttu-id="23b3f-121">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="23b3f-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="23b3f-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="23b3f-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="23b3f-123">Debug</span><span class="sxs-lookup"><span data-stu-id="23b3f-123">Debugging</span></span>](index.md)
