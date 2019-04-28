---
title: Metodo ICorDebugCode::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750208"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="dfaf5-102">Metodo ICorDebugCode::GetSize</span><span class="sxs-lookup"><span data-stu-id="dfaf5-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="dfaf5-103">Ottiene la dimensione, espressa in byte, del codice binario rappresentato da "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="dfaf5-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfaf5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfaf5-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfaf5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dfaf5-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="dfaf5-106">[out] Un puntatore alla dimensione, espressa in byte, del file binario di codice che questo `ICorDebugCode` oggetto rappresenta.</span><span class="sxs-lookup"><span data-stu-id="dfaf5-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfaf5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfaf5-107">Requirements</span></span>  
 <span data-ttu-id="dfaf5-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfaf5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfaf5-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfaf5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfaf5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfaf5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfaf5-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfaf5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfaf5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfaf5-112">See also</span></span>
