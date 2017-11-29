---
title: Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ca1514eaa916f5e607e49b5a5713763f855d937
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="d8754-102">Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d8754-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="d8754-103">Rimuove un impostata in precedenza punto di interruzione in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="d8754-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8754-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8754-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8754-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8754-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d8754-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in cui è stato impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d8754-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8754-107">Note</span><span class="sxs-lookup"><span data-stu-id="d8754-107">Remarks</span></span>  
 <span data-ttu-id="d8754-108">Il punto di interruzione specificato sarebbe stato impostato precedentemente da una precedente chiamata a [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="d8754-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="d8754-109">Il `ClearUnmanagedBreakpoint` metodo può essere chiamato mentre è in esecuzione il processo sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="d8754-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="d8754-110">Il `ClearUnmanagedBreakpoint` metodo restituisce un codice di errore se il debugger è collegato in modalità solo gestito o se è presente alcun punto di interruzione in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="d8754-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8754-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8754-111">Requirements</span></span>  
 <span data-ttu-id="d8754-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8754-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8754-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d8754-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8754-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8754-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8754-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8754-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
