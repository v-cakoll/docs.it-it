---
title: Metodo ICorDebugManagedCallback::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: d773368c85fd42fd169109cf1c7e6635705ebb7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090233"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="d88c8-102">Metodo ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="d88c8-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="d88c8-103">Notifica al debugger il momento in cui un processo è stato collegato o avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="d88c8-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d88c8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d88c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d88c8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d88c8-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo collegato o avviato.</span><span class="sxs-lookup"><span data-stu-id="d88c8-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d88c8-107">Note</span><span class="sxs-lookup"><span data-stu-id="d88c8-107">Remarks</span></span>  
 <span data-ttu-id="d88c8-108">Questo metodo non viene chiamato fino a quando non viene inizializzata la Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d88c8-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="d88c8-109">La maggior parte dei metodi di [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) restituirà CORDBG_E_NOTREADY prima del callback `CreateProcess`.</span><span class="sxs-lookup"><span data-stu-id="d88c8-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d88c8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d88c8-110">Requirements</span></span>  
 <span data-ttu-id="d88c8-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d88c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d88c8-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d88c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d88c8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d88c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d88c8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d88c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88c8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d88c8-115">See also</span></span>

- [<span data-ttu-id="d88c8-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d88c8-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
