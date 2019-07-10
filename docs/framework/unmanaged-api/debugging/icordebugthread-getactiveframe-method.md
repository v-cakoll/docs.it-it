---
title: Metodo ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390a2c64508bf407296d318a47bfd2972b7ef9d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762555"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="12fa1-102">Metodo ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="12fa1-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="12fa1-103">Ottiene un puntatore a interfaccia per il frame attivo (più recente) tohoto objektu ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="12fa1-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12fa1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12fa1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12fa1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="12fa1-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="12fa1-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugFrame che rappresenta un frame.</span><span class="sxs-lookup"><span data-stu-id="12fa1-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12fa1-107">Note</span><span class="sxs-lookup"><span data-stu-id="12fa1-107">Remarks</span></span>  
 <span data-ttu-id="12fa1-108">Il `ppFrame` parametro è null se nessun frame è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="12fa1-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12fa1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12fa1-109">Requirements</span></span>  
 <span data-ttu-id="12fa1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12fa1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12fa1-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12fa1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12fa1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12fa1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12fa1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12fa1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
