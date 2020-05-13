---
title: Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: d2fc59621cbb6752830c7a8392ce4e0c476ef9e7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210059"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="e9b4c-102">Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="e9b4c-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="e9b4c-103">Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9b4c-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9b4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9b4c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e9b4c-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene la funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e9b4c-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione del mapping.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="e9b4c-108">in Puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione nel thread.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="e9b4c-109">in Puntatore a un oggetto ICorDebugFunction che rappresenta la versione più recente della funzione.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="e9b4c-110">in Offset MSIL (Microsoft Intermediate Language) del puntatore all'istruzione nella versione precedente della funzione.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b4c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e9b4c-111">Remarks</span></span>  
 <span data-ttu-id="e9b4c-112">Questo callback offre al debugger un'opportunità per modificare il mapping del puntatore all'istruzione alla posizione corretta nella nuova versione della funzione specificata chiamando il metodo [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9b4c-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="e9b4c-113">Se il debugger non chiama `RemapFunction` prima di chiamare il metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) , il runtime continuerà a eseguire il codice precedente e genererà un altro `FunctionRemapOpportunity` callback al successivo punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="e9b4c-114">Questo callback verrà richiamato per ogni frame che esegue una versione precedente della funzione specificata fino a quando il debugger non restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="e9b4c-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b4c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9b4c-115">Requirements</span></span>  
 <span data-ttu-id="e9b4c-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9b4c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b4c-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9b4c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9b4c-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b4c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b4c-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b4c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b4c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b4c-120">See also</span></span>

- [<span data-ttu-id="e9b4c-121">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="e9b4c-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e9b4c-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e9b4c-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
