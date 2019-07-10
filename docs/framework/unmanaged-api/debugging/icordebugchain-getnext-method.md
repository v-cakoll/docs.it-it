---
title: Metodo ICorDebugChain::GetNext
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 990786fbb3cc853f7f399d60fa686bb5d60018af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745705"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="fbab5-102">Metodo ICorDebugChain::GetNext</span><span class="sxs-lookup"><span data-stu-id="fbab5-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="fbab5-103">Ottiene la catena di frame successiva per il thread.</span><span class="sxs-lookup"><span data-stu-id="fbab5-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbab5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbab5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbab5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fbab5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="fbab5-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di frame per il thread successiva.</span><span class="sxs-lookup"><span data-stu-id="fbab5-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="fbab5-107">Se questa è l'ultimo catena, `ppChain` è null.</span><span class="sxs-lookup"><span data-stu-id="fbab5-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbab5-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbab5-108">Requirements</span></span>  
 <span data-ttu-id="fbab5-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbab5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbab5-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbab5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbab5-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbab5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbab5-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbab5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
