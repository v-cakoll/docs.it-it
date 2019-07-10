---
title: Metodo ICorDebugThread::GetActiveChain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59328c8b7e86694610de20ade72a98a4280b439d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762625"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="7eb5d-102">Metodo ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="7eb5d-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="7eb5d-103">Ottiene un puntatore a interfaccia alla catena dello stack (più recente) attiva tohoto objektu ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="7eb5d-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7eb5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eb5d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7eb5d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="7eb5d-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena dello stack.</span><span class="sxs-lookup"><span data-stu-id="7eb5d-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eb5d-107">Note</span><span class="sxs-lookup"><span data-stu-id="7eb5d-107">Remarks</span></span>  
 <span data-ttu-id="7eb5d-108">Il `ppChain` parametro è null se nessun catena dello stack è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="7eb5d-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb5d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7eb5d-109">Requirements</span></span>  
 <span data-ttu-id="7eb5d-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb5d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7eb5d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eb5d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eb5d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eb5d-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb5d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
