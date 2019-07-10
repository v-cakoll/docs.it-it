---
title: Metodo ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f801dae69f16f2848b4ffa30f458c084fe9750a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754890"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="927b2-102">Metodo ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="927b2-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="927b2-103">Ottiene la funzione che contiene il codice associato a questo frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="927b2-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="927b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="927b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="927b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="927b2-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="927b2-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFunction che rappresenta la funzione che contiene il codice associato a questo frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="927b2-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="927b2-107">Note</span><span class="sxs-lookup"><span data-stu-id="927b2-107">Remarks</span></span>  
 <span data-ttu-id="927b2-108">Il `GetFunction` metodo potrebbe non riuscire se il frame non è associato ad alcuna funzione particolare.</span><span class="sxs-lookup"><span data-stu-id="927b2-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="927b2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="927b2-109">Requirements</span></span>  
 <span data-ttu-id="927b2-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="927b2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="927b2-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="927b2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="927b2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="927b2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="927b2-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="927b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
