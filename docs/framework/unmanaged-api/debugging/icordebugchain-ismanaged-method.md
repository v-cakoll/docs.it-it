---
title: Metodo ICorDebugChain::IsManaged
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
ms.openlocfilehash: 55036fcdbd186f91c0e94fb05f3023cf614751f7
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894245"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="4bce8-102">Metodo ICorDebugChain::IsManaged</span><span class="sxs-lookup"><span data-stu-id="4bce8-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="4bce8-103">Ottiene un valore che indica se la catena sta eseguendo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4bce8-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bce8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bce8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bce8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bce8-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="4bce8-106">out `true` se questa catena sta eseguendo codice gestito; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="4bce8-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bce8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bce8-107">Requirements</span></span>  
 <span data-ttu-id="4bce8-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bce8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bce8-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bce8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bce8-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bce8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bce8-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bce8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
