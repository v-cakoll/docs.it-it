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
ms.openlocfilehash: e2aaf902afd71a4a81f7d64ef3fec046aacc91fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792537"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="06714-102">Metodo ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="06714-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="06714-103">Rimuove un punto di interruzione impostato in precedenza in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="06714-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06714-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06714-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06714-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06714-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="06714-106">in Valore `CORDB_ADDRESS` che specifica l'indirizzo in corrispondenza del quale è stato impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="06714-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06714-107">Note</span><span class="sxs-lookup"><span data-stu-id="06714-107">Remarks</span></span>  
 <span data-ttu-id="06714-108">Il punto di interruzione specificato è stato impostato in precedenza da una chiamata precedente a [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="06714-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="06714-109">È possibile chiamare il metodo `ClearUnmanagedBreakpoint` mentre è in esecuzione il processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="06714-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="06714-110">Il metodo `ClearUnmanagedBreakpoint` restituisce un codice di errore se il debugger è collegato in modalità solo gestito oppure se non esiste alcun punto di interruzione nell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="06714-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06714-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="06714-111">Requirements</span></span>  
 <span data-ttu-id="06714-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06714-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06714-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06714-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06714-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06714-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06714-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06714-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
