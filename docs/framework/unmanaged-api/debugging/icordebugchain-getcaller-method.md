---
title: Metodo ICorDebugChain::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: 5a07550d44857526e8ab4ded9f1827ef12e3bba4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192140"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="6172a-102">Metodo ICorDebugChain::GetCaller</span><span class="sxs-lookup"><span data-stu-id="6172a-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="6172a-103">Ottiene la catena che ha chiamato questa catena.</span><span class="sxs-lookup"><span data-stu-id="6172a-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6172a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6172a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6172a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6172a-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="6172a-106">out Puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena chiamante.</span><span class="sxs-lookup"><span data-stu-id="6172a-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="6172a-107">Se questa catena è stata chiamata in modo spontaneo (come nel caso in cui la catena o il debugger ha inizializzato lo stack di chiamate), `ppChain` sarà null.</span><span class="sxs-lookup"><span data-stu-id="6172a-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6172a-108">Note</span><span class="sxs-lookup"><span data-stu-id="6172a-108">Remarks</span></span>  
 <span data-ttu-id="6172a-109">La catena chiamante può trovarsi in un thread diverso, se la chiamata è stata sottoposta a marshalling tra thread.</span><span class="sxs-lookup"><span data-stu-id="6172a-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6172a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6172a-110">Requirements</span></span>  
 <span data-ttu-id="6172a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6172a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6172a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6172a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6172a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6172a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6172a-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6172a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
