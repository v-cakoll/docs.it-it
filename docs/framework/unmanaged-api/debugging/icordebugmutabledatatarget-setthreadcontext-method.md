---
title: 'Metodo ICorDebugMutableDataTarget:: SetThreadContext'
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 2c9e508c7a4059fee4e1cce6eb28e6de7b2fff6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132711"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="e0fff-102">Metodo ICorDebugMutableDataTarget:: SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="e0fff-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="e0fff-103">Imposta il contesto (valori del registro) per un thread.</span><span class="sxs-lookup"><span data-stu-id="e0fff-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0fff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0fff-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0fff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0fff-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="e0fff-106">[in] Identificatore del thread definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e0fff-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e0fff-107">[in] Dimensioni del buffer `pContext` da scrivere.</span><span class="sxs-lookup"><span data-stu-id="e0fff-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="e0fff-108">[in] Puntatore ai byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="e0fff-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0fff-109">Note</span><span class="sxs-lookup"><span data-stu-id="e0fff-109">Remarks</span></span>  
 <span data-ttu-id="e0fff-110">Il metodo `SetThreadContext` aggiorna il contesto corrente per il thread specificato dall'argomento `dwThreadID` definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e0fff-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="e0fff-111">Il formato del record di contesto è determinato dalla piattaforma indicata dal metodo [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0fff-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="e0fff-112">In Windows si tratta di una struttura di [contesto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="e0fff-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0fff-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0fff-113">Requirements</span></span>  
 <span data-ttu-id="e0fff-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0fff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0fff-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0fff-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0fff-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0fff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0fff-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0fff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0fff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0fff-118">See also</span></span>

- [<span data-ttu-id="e0fff-119">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="e0fff-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="e0fff-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e0fff-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
