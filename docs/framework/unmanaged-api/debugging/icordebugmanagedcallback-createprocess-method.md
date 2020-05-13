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
ms.openlocfilehash: 0e9ed8054711297173e880c9eecb12c3f5bd0a68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207128"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="c59ee-102">Metodo ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="c59ee-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="c59ee-103">Notifica al debugger il momento in cui un processo è stato collegato o avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="c59ee-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c59ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c59ee-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c59ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c59ee-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c59ee-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo collegato o avviato.</span><span class="sxs-lookup"><span data-stu-id="c59ee-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c59ee-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c59ee-107">Remarks</span></span>  
 <span data-ttu-id="c59ee-108">Questo metodo non viene chiamato fino a quando non viene inizializzata la Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c59ee-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="c59ee-109">La maggior parte dei metodi [ICorDebug](icordebug-interface.md) restituirà CORDBG_E_NOTREADY prima del `CreateProcess` callback.</span><span class="sxs-lookup"><span data-stu-id="c59ee-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c59ee-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c59ee-110">Requirements</span></span>  
 <span data-ttu-id="c59ee-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c59ee-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c59ee-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c59ee-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c59ee-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c59ee-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c59ee-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c59ee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59ee-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c59ee-115">See also</span></span>

- [<span data-ttu-id="c59ee-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c59ee-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
