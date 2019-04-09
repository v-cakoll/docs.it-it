---
title: Metodo ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8b3fd9940bd11c3d026b46247e0657c82b18099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120003"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="ff6a5-102">Metodo ICorDebugMutableDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="ff6a5-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="ff6a5-103">Imposta il contesto (valori del registro) per un thread.</span><span class="sxs-lookup"><span data-stu-id="ff6a5-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff6a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff6a5-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff6a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff6a5-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="ff6a5-106">[in] Identificatore del thread definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ff6a5-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ff6a5-107">[in] Dimensioni del buffer `pContext` da scrivere.</span><span class="sxs-lookup"><span data-stu-id="ff6a5-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="ff6a5-108">[in] Puntatore ai byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="ff6a5-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff6a5-109">Note</span><span class="sxs-lookup"><span data-stu-id="ff6a5-109">Remarks</span></span>  
 <span data-ttu-id="ff6a5-110">Il metodo `SetThreadContext` aggiorna il contesto corrente per il thread specificato dall'argomento `dwThreadID` definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ff6a5-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="ff6a5-111">Il formato del record di contesto è determinato dalla piattaforma indicata per la [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ff6a5-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="ff6a5-112">In Windows, si tratta di un [contesto](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) struttura.</span><span class="sxs-lookup"><span data-stu-id="ff6a5-112">On Windows, this is a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff6a5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff6a5-113">Requirements</span></span>  
 <span data-ttu-id="ff6a5-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff6a5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff6a5-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff6a5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff6a5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff6a5-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ff6a5-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ff6a5-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff6a5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff6a5-118">See also</span></span>

- [<span data-ttu-id="ff6a5-119">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="ff6a5-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="ff6a5-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ff6a5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
