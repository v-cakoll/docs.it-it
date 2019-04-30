---
title: Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4dcfb977f5ca87f2219fd3ed8ef87d16c2defd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948967"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="5be34-102">Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5be34-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="5be34-103">Rimuove un impostato in precedenza punto di interruzione in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="5be34-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5be34-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5be34-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5be34-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5be34-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in corrispondenza del quale è stato impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="5be34-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5be34-107">Note</span><span class="sxs-lookup"><span data-stu-id="5be34-107">Remarks</span></span>  
 <span data-ttu-id="5be34-108">Il punto di interruzione specificato sarebbe stato impostato precedentemente da una precedente chiamata a [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="5be34-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="5be34-109">Il `ClearUnmanagedBreakpoint` metodo può essere chiamato mentre è in esecuzione il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="5be34-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="5be34-110">Il `ClearUnmanagedBreakpoint` metodo restituisce un codice di errore se il debugger è collegato in modalità "solo gestito" o se è presente alcun punto di interruzione in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="5be34-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5be34-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5be34-111">Requirements</span></span>  
 <span data-ttu-id="5be34-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5be34-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5be34-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5be34-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5be34-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5be34-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5be34-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5be34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
