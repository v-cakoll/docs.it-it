---
title: Metodo ICorDebugChain::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745016"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="9daf4-102">Metodo ICorDebugChain::GetCallee</span><span class="sxs-lookup"><span data-stu-id="9daf4-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="9daf4-103">Ottiene la catena di chiamata da questa catena.</span><span class="sxs-lookup"><span data-stu-id="9daf4-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9daf4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9daf4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9daf4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9daf4-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="9daf4-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamate.</span><span class="sxs-lookup"><span data-stu-id="9daf4-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="9daf4-107">Se la catena è attualmente in esecuzione (vale a dire se questa catena non è in attesa di una catena di chiamata), `ppChain` sarà null.</span><span class="sxs-lookup"><span data-stu-id="9daf4-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9daf4-108">Note</span><span class="sxs-lookup"><span data-stu-id="9daf4-108">Remarks</span></span>  
 <span data-ttu-id="9daf4-109">Questa catena attenderà la catena di chiamata restituire prima di riprendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9daf4-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="9daf4-110">La catena di chiamate potrebbe essere in un altro thread nel caso di chiamate per il marshalling cross-thread.</span><span class="sxs-lookup"><span data-stu-id="9daf4-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9daf4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9daf4-111">Requirements</span></span>  
 <span data-ttu-id="9daf4-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9daf4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9daf4-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9daf4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9daf4-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9daf4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9daf4-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9daf4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
