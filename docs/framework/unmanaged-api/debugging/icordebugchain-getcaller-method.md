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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645279"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="d2e72-102">Metodo ICorDebugChain::GetCaller</span><span class="sxs-lookup"><span data-stu-id="d2e72-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="d2e72-103">Ottiene la catena che ha chiamato questa catena.</span><span class="sxs-lookup"><span data-stu-id="d2e72-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2e72-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2e72-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2e72-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="d2e72-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d2e72-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="d2e72-107">Se questa catena è stata chiamata spontaneamente (come sarebbe il caso se questa catena o il debugger inizializzata nello stack di chiamate), `ppChain` sarà null.</span><span class="sxs-lookup"><span data-stu-id="d2e72-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2e72-108">Note</span><span class="sxs-lookup"><span data-stu-id="d2e72-108">Remarks</span></span>  
 <span data-ttu-id="d2e72-109">La catena di chiamata può essere su un thread diverso, se è stato effettuato il marshalling della chiamata tra thread.</span><span class="sxs-lookup"><span data-stu-id="d2e72-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e72-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2e72-110">Requirements</span></span>  
 <span data-ttu-id="d2e72-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2e72-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2e72-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2e72-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2e72-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2e72-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2e72-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2e72-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
