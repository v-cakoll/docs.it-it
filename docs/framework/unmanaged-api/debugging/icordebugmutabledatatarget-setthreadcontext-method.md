---
title: Metodo ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 063c7954543174caece6f3dcbe005a4b2d059c64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792839"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="eb941-102">Metodo ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="eb941-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="eb941-103">Imposta il contesto (valori del registro) per un thread.</span><span class="sxs-lookup"><span data-stu-id="eb941-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb941-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb941-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb941-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb941-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="eb941-106">[in] Identificatore del thread definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eb941-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="eb941-107">[in] Dimensioni del buffer `pContext` da scrivere.</span><span class="sxs-lookup"><span data-stu-id="eb941-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="eb941-108">[in] Puntatore ai byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="eb941-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb941-109">Note</span><span class="sxs-lookup"><span data-stu-id="eb941-109">Remarks</span></span>  
 <span data-ttu-id="eb941-110">Il metodo `SetThreadContext` aggiorna il contesto corrente per il thread specificato dall'argomento `dwThreadID` definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eb941-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="eb941-111">Il formato del record di contesto è determinato dalla piattaforma indicata dal metodo [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb941-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="eb941-112">In Windows si tratta di una struttura di [contesto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="eb941-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb941-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="eb941-113">Requirements</span></span>  
 <span data-ttu-id="eb941-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb941-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb941-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb941-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb941-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb941-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb941-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb941-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb941-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb941-118">See also</span></span>

- [<span data-ttu-id="eb941-119">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="eb941-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="eb941-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="eb941-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
