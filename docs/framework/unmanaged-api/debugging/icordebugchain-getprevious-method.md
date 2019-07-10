---
title: Metodo ICorDebugChain::GetPrevious
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31c795c2fbbfdc45b6e1aac6684f730f55fc106a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746412"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="04670-102">Metodo ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="04670-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="04670-103">Ottiene la catena di frame precedente per il thread.</span><span class="sxs-lookup"><span data-stu-id="04670-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04670-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04670-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04670-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="04670-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="04670-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di frame per il thread precedente.</span><span class="sxs-lookup"><span data-stu-id="04670-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="04670-107">Se questa è la prima catena `ppChain` è null.</span><span class="sxs-lookup"><span data-stu-id="04670-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04670-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04670-108">Requirements</span></span>  
 <span data-ttu-id="04670-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04670-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04670-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04670-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04670-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04670-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04670-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04670-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
