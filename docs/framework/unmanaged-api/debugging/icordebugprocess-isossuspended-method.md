---
title: Metodo ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775563"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="80fe4-102">Metodo ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="80fe4-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="80fe4-103">Ottiene un valore che indica se il thread specificato è stata sospesa in seguito il debugger di interruzione del processo.</span><span class="sxs-lookup"><span data-stu-id="80fe4-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fe4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80fe4-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80fe4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80fe4-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="80fe4-106">[in] L'ID del thread in questione.</span><span class="sxs-lookup"><span data-stu-id="80fe4-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="80fe4-107">[out] Un puntatore a un valore booleano che è `true` se il thread specificato è stata sospesa; in caso contrario \*`pbSuspended` è `false`.</span><span class="sxs-lookup"><span data-stu-id="80fe4-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80fe4-108">Note</span><span class="sxs-lookup"><span data-stu-id="80fe4-108">Remarks</span></span>  
 <span data-ttu-id="80fe4-109">Quando il thread specificato è stata sospesa in seguito il debugger di interruzione del processo, un conteggio di sospensione Win32 del thread specificato viene incrementato di uno.</span><span class="sxs-lookup"><span data-stu-id="80fe4-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="80fe4-110">L'interfaccia utente del debugger (UI) potrebbe voler sfruttare queste informazioni in considerazione se viene visualizzato il sistema operativo (OS) sospendere conteggio dei thread per l'utente.</span><span class="sxs-lookup"><span data-stu-id="80fe4-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="80fe4-111">Il `IsOSSuspended` metodo senso solo nel contesto di debug non gestito.</span><span class="sxs-lookup"><span data-stu-id="80fe4-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="80fe4-112">Durante il debug gestito, i thread sono in modo cooperativo sospeso anziché sospeso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="80fe4-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fe4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80fe4-113">Requirements</span></span>  
 <span data-ttu-id="80fe4-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80fe4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fe4-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80fe4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80fe4-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80fe4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80fe4-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80fe4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
