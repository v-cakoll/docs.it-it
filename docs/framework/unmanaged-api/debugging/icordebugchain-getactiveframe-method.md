---
title: Metodo ICorDebugChain::GetActiveFrame
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7498e031b74bd904b908342b663e4421432e6d95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="208e0-102">Metodo ICorDebugChain::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="208e0-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="208e0-103">Ottiene attivo (vale a dire più recente) frame sulla catena.</span><span class="sxs-lookup"><span data-stu-id="208e0-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="208e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="208e0-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="208e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="208e0-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="208e0-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFrame che rappresenta l'attivo (vale a dire più recente) frame sulla catena.</span><span class="sxs-lookup"><span data-stu-id="208e0-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="208e0-107">Note</span><span class="sxs-lookup"><span data-stu-id="208e0-107">Remarks</span></span>  
 <span data-ttu-id="208e0-108">Se non è disponibile alcun frame dello stack gestito `ppFrame` è impostato su null.</span><span class="sxs-lookup"><span data-stu-id="208e0-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="208e0-109">Se il frame attivo non è disponibile, la chiamata avrà esito positivo e `ppFrame` sarà null.</span><span class="sxs-lookup"><span data-stu-id="208e0-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="208e0-110">Non sarà disponibili per le catene avviate da CHAIN_ENTER_UNMANAGED e per alcune catene avviate CHAIN_CLASS_INIT frame attivi.</span><span class="sxs-lookup"><span data-stu-id="208e0-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="208e0-111">Vedere l'enumerazione CorDebugChainReason.</span><span class="sxs-lookup"><span data-stu-id="208e0-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="208e0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="208e0-112">Requirements</span></span>  
 <span data-ttu-id="208e0-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="208e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="208e0-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="208e0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="208e0-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="208e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="208e0-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="208e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
