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
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791967"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="70416-102">Metodo ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="70416-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="70416-103">Avvia un processo in un computer remoto nel debugger.</span><span class="sxs-lookup"><span data-stu-id="70416-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70416-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70416-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70416-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="70416-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="70416-106">in Puntatore a un' [interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="70416-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="70416-107">Questo parametro viene utilizzato per determinare il computer in cui è in esecuzione il processo.</span><span class="sxs-lookup"><span data-stu-id="70416-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="70416-108">in ID del processo a cui deve essere collegato il debugger.</span><span class="sxs-lookup"><span data-stu-id="70416-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="70416-109">[in] `true` se il debugger deve comportarsi come debugger Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="70416-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="70416-110">out Puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato collegato il debugger.</span><span class="sxs-lookup"><span data-stu-id="70416-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70416-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="70416-111">Return Value</span></span>  
 <span data-ttu-id="70416-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="70416-112">S_OK</span></span>  
 <span data-ttu-id="70416-113">La connessione al processo nel computer remoto è stata completata.</span><span class="sxs-lookup"><span data-stu-id="70416-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="70416-114">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="70416-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="70416-115">Impossibile connettersi al processo nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="70416-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70416-116">Note</span><span class="sxs-lookup"><span data-stu-id="70416-116">Remarks</span></span>  
 <span data-ttu-id="70416-117">Il debug in modalità mista non è supportato in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="70416-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70416-118">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="70416-118">Requirements</span></span>  
 <span data-ttu-id="70416-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70416-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70416-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70416-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70416-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70416-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70416-122">**Versioni .NET Framework:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="70416-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70416-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70416-123">See also</span></span>

- [<span data-ttu-id="70416-124">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="70416-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="70416-125">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="70416-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="70416-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="70416-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
