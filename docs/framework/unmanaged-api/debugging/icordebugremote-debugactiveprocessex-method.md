---
title: Metodo ICorDebugRemote::DebugActiveProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e3cdbff5054ec990c40c333ed4bd4029a91f12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420804"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="bfe15-102">Metodo ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="bfe15-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="bfe15-103">Avvia un processo in un computer remoto all'interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="bfe15-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfe15-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfe15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bfe15-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="bfe15-106">[in] Puntatore a un [ICorDebugRemoteTarget (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bfe15-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="bfe15-107">Questo parametro viene utilizzato per determinare il computer in cui viene eseguito il processo.</span><span class="sxs-lookup"><span data-stu-id="bfe15-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="bfe15-108">[in] L'ID del processo a cui il debugger deve essere collegato.</span><span class="sxs-lookup"><span data-stu-id="bfe15-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="bfe15-109">[in] `true` se il debugger deve comportarsi come il debugger di Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="bfe15-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="bfe15-110">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato connesso il debugger.</span><span class="sxs-lookup"><span data-stu-id="bfe15-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfe15-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bfe15-111">Return Value</span></span>  
 <span data-ttu-id="bfe15-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfe15-112">S_OK</span></span>  
 <span data-ttu-id="bfe15-113">È stato collegato al processo nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="bfe15-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="bfe15-114">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="bfe15-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="bfe15-115">Impossibile connettersi al processo nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="bfe15-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe15-116">Note</span><span class="sxs-lookup"><span data-stu-id="bfe15-116">Remarks</span></span>  
 <span data-ttu-id="bfe15-117">Debug in modalità mista non è supportato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="bfe15-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe15-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfe15-118">Requirements</span></span>  
 <span data-ttu-id="bfe15-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfe15-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe15-120">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bfe15-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfe15-121">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bfe15-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfe15-122">**Versioni di .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bfe15-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe15-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe15-123">See Also</span></span>  
 [<span data-ttu-id="bfe15-124">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="bfe15-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="bfe15-125">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="bfe15-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="bfe15-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bfe15-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
