---
title: Metodo ICorDebugArrayValue::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e45f49d17a5b71abfb58ff8c0126abad49322c5b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737592"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="13180-102">Metodo ICorDebugArrayValue::GetCount</span><span class="sxs-lookup"><span data-stu-id="13180-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="13180-103">Ottiene il numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="13180-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13180-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13180-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13180-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13180-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="13180-106">[out] Puntatore al numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="13180-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13180-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13180-107">Requirements</span></span>  
 <span data-ttu-id="13180-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13180-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13180-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13180-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13180-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13180-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13180-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13180-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
