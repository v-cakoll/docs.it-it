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
ms.openlocfilehash: ba9a4e32216fd6fad285397bfc48fbc54f602b88
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894655"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="1af8c-102">Metodo ICorDebugChain::GetCallee</span><span class="sxs-lookup"><span data-stu-id="1af8c-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="1af8c-103">Ottiene la catena chiamata dalla catena.</span><span class="sxs-lookup"><span data-stu-id="1af8c-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1af8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1af8c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1af8c-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="1af8c-106">out Puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena chiamata.</span><span class="sxs-lookup"><span data-stu-id="1af8c-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="1af8c-107">Se questa catena è attualmente in esecuzione (ovvero se questa catena non è in attesa della restituzione di una catena chiamata), `ppChain` sarà null.</span><span class="sxs-lookup"><span data-stu-id="1af8c-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1af8c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1af8c-108">Remarks</span></span>  
 <span data-ttu-id="1af8c-109">Questa catena attende che la catena chiamata restituisca prima di riprendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1af8c-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="1af8c-110">La catena chiamata può trovarsi in un altro thread nel caso di chiamate con marshalling tra thread.</span><span class="sxs-lookup"><span data-stu-id="1af8c-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af8c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1af8c-111">Requirements</span></span>  
 <span data-ttu-id="1af8c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1af8c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af8c-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1af8c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1af8c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1af8c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1af8c-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
