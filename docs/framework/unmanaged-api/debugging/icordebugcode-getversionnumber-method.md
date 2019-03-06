---
title: Metodo ICorDebugCode::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e1f67dde8193ff97bff835f4b653a61baa0a2d7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487785"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="2fd89-102">Metodo ICorDebugCode::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="2fd89-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="2fd89-103">Ottiene il numero in base 1 che identifica la versione del codice che rappresenta "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="2fd89-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fd89-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fd89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2fd89-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="2fd89-106">[out] Puntatore al numero di versione del codice.</span><span class="sxs-lookup"><span data-stu-id="2fd89-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fd89-107">Note</span><span class="sxs-lookup"><span data-stu-id="2fd89-107">Remarks</span></span>  
 <span data-ttu-id="2fd89-108">Il numero di versione viene incrementato ogni volta che modifica e continuazione (EnC) è un'operazione sul codice.</span><span class="sxs-lookup"><span data-stu-id="2fd89-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd89-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fd89-109">Requirements</span></span>  
 <span data-ttu-id="2fd89-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fd89-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd89-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fd89-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fd89-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fd89-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fd89-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd89-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd89-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fd89-114">See also</span></span>

