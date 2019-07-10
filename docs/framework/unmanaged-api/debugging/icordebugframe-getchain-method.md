---
title: Metodo ICorDebugFrame::GetChain
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64de770676cdd02375e854acb8af7feecb28dfeb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754106"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="64f5e-102">Metodo ICorDebugFrame::GetChain</span><span class="sxs-lookup"><span data-stu-id="64f5e-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="64f5e-103">Ottiene un puntatore per il frame è una parte della catena.</span><span class="sxs-lookup"><span data-stu-id="64f5e-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f5e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64f5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64f5e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64f5e-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="64f5e-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena che contiene il frame.</span><span class="sxs-lookup"><span data-stu-id="64f5e-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64f5e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64f5e-107">Requirements</span></span>  
 <span data-ttu-id="64f5e-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64f5e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64f5e-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64f5e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64f5e-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64f5e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64f5e-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64f5e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
