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
ms.openlocfilehash: 52ba9d5bac5e772d721d38e4e8a7ba6757d0ae2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747498"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="b6fbf-102">Metodo ICorDebugCode::GetSize</span><span class="sxs-lookup"><span data-stu-id="b6fbf-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="b6fbf-103">Ottiene la dimensione, espressa in byte, del codice binario rappresentato da "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="b6fbf-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6fbf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6fbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6fbf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6fbf-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="b6fbf-106">[out] Un puntatore alla dimensione, espressa in byte, del file binario di codice che questo `ICorDebugCode` oggetto rappresenta.</span><span class="sxs-lookup"><span data-stu-id="b6fbf-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6fbf-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6fbf-107">Requirements</span></span>  
 <span data-ttu-id="b6fbf-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6fbf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6fbf-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6fbf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6fbf-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6fbf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6fbf-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6fbf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fbf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6fbf-112">See also</span></span>
