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
ms.openlocfilehash: 0c3059697014cea33081f6cb81b9d93c7d028c2e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777473"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="19438-102">Metodo ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="19438-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="19438-103">Notifica al debugger il momento in cui un processo è stato collegato o avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="19438-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19438-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19438-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19438-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19438-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="19438-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo collegato o avviato.</span><span class="sxs-lookup"><span data-stu-id="19438-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19438-107">Note</span><span class="sxs-lookup"><span data-stu-id="19438-107">Remarks</span></span>  
 <span data-ttu-id="19438-108">Questo metodo non viene chiamato fino a quando non viene inizializzata la Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="19438-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="19438-109">La maggior parte dei metodi di [ICorDebug](icordebug-interface.md) restituirà CORDBG_E_NOTREADY prima del callback di `CreateProcess`.</span><span class="sxs-lookup"><span data-stu-id="19438-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19438-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="19438-110">Requirements</span></span>  
 <span data-ttu-id="19438-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19438-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19438-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19438-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19438-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19438-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19438-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19438-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19438-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19438-115">See also</span></span>

- [<span data-ttu-id="19438-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="19438-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
