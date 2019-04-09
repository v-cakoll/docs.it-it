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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda214200ca4c3837ad89ed14887ef6b09af7d30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160368"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="84922-102">Metodo ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="84922-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="84922-103">Quando un processo è stato collegato o avviato per la prima volta, invia una notifica del debugger.</span><span class="sxs-lookup"><span data-stu-id="84922-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84922-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84922-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84922-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84922-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="84922-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo di cui è stato collegato o avviato.</span><span class="sxs-lookup"><span data-stu-id="84922-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84922-107">Note</span><span class="sxs-lookup"><span data-stu-id="84922-107">Remarks</span></span>  
 <span data-ttu-id="84922-108">Questo metodo non viene chiamato fino a quando non viene inizializzato in common language runtime.</span><span class="sxs-lookup"><span data-stu-id="84922-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="84922-109">La maggior parte delle [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) metodi restituiranno CORDBG_E_NOTREADY prima il `CreateProcess` callback.</span><span class="sxs-lookup"><span data-stu-id="84922-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84922-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84922-110">Requirements</span></span>  
 <span data-ttu-id="84922-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84922-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84922-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84922-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84922-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84922-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="84922-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="84922-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84922-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84922-115">See also</span></span>

- [<span data-ttu-id="84922-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="84922-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
