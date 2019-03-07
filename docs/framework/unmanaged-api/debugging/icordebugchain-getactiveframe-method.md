---
title: Metodo ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14b48a29993a65a0a0ab9fcb63bcb1e0d882042
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494070"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="fde44-102">Metodo ICorDebugChain::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="fde44-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="fde44-103">Ottiene attivo (vale a dire più recente) frame della catena.</span><span class="sxs-lookup"><span data-stu-id="fde44-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fde44-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fde44-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fde44-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="fde44-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFrame rappresenta attivo (vale a dire più recente) frame della catena.</span><span class="sxs-lookup"><span data-stu-id="fde44-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fde44-107">Note</span><span class="sxs-lookup"><span data-stu-id="fde44-107">Remarks</span></span>  
 <span data-ttu-id="fde44-108">Se non è disponibile alcun stack frame gestito `ppFrame` è impostato su null.</span><span class="sxs-lookup"><span data-stu-id="fde44-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="fde44-109">Se il frame attivo non è disponibile, la chiamata avrà esito positivo e `ppFrame` sarà null.</span><span class="sxs-lookup"><span data-stu-id="fde44-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="fde44-110">Non sarà disponibili per catene avviate da CHAIN_ENTER_UNMANAGED e per alcuni catene avviate da CHAIN_CLASS_INIT frame attivi.</span><span class="sxs-lookup"><span data-stu-id="fde44-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="fde44-111">Vedere l'enumerazione CorDebugChainReason.</span><span class="sxs-lookup"><span data-stu-id="fde44-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde44-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fde44-112">Requirements</span></span>  
 <span data-ttu-id="fde44-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fde44-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde44-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fde44-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fde44-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fde44-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fde44-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
