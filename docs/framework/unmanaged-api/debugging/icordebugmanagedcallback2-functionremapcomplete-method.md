---
title: Metodo ICorDebugManagedCallback2::FunctionRemapComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: d49992b1f4b25586f6171a51b351a25d453560f2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212152"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="6d268-102">Metodo ICorDebugManagedCallback2::FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="6d268-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="6d268-103">Notifica al debugger che l'esecuzione del codice è cambiata a una nuova versione di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="6d268-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d268-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d268-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d268-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d268-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6d268-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene la funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="6d268-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6d268-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione del mapping.</span><span class="sxs-lookup"><span data-stu-id="6d268-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="6d268-108">in Puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione nel thread.</span><span class="sxs-lookup"><span data-stu-id="6d268-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d268-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6d268-109">Remarks</span></span>  
 <span data-ttu-id="6d268-110">Questo callback offre al debugger un'opportunità per ricreare eventuali stepper che in precedenza erano disponibili.</span><span class="sxs-lookup"><span data-stu-id="6d268-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d268-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d268-111">Requirements</span></span>  
 <span data-ttu-id="6d268-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d268-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d268-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d268-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d268-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d268-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d268-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d268-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d268-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d268-116">See also</span></span>

- [<span data-ttu-id="6d268-117">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="6d268-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="6d268-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6d268-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
