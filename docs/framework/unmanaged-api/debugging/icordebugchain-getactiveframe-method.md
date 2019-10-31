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
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192150"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="4b76e-102">Metodo ICorDebugChain::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="4b76e-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="4b76e-103">Ottiene il frame attivo (ovvero, più recente) nella catena.</span><span class="sxs-lookup"><span data-stu-id="4b76e-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b76e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b76e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b76e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b76e-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="4b76e-106">out Puntatore all'indirizzo di un oggetto ICorDebugFrame che rappresenta il frame attivo (ovvero il più recente) nella catena.</span><span class="sxs-lookup"><span data-stu-id="4b76e-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b76e-107">Note</span><span class="sxs-lookup"><span data-stu-id="4b76e-107">Remarks</span></span>  
 <span data-ttu-id="4b76e-108">Se non è disponibile alcun stack frame gestito, `ppFrame` è impostato su null.</span><span class="sxs-lookup"><span data-stu-id="4b76e-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="4b76e-109">Se il frame attivo non è disponibile, la chiamata avrà esito positivo e `ppFrame` sarà null.</span><span class="sxs-lookup"><span data-stu-id="4b76e-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="4b76e-110">I frame attivi non saranno disponibili per le catene avviate a causa di CHAIN_ENTER_UNMANAGED e per alcune catene avviate a causa di CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="4b76e-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="4b76e-111">Vedere l'enumerazione CorDebugChainReason.</span><span class="sxs-lookup"><span data-stu-id="4b76e-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b76e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b76e-112">Requirements</span></span>  
 <span data-ttu-id="4b76e-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b76e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b76e-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b76e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b76e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b76e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b76e-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b76e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
