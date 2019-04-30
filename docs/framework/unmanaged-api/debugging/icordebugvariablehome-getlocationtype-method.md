---
title: Metodo ICorDebugVariableHome::GetLocationType
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af879cbbf8edfd05e79d9b77b0c1fb71b2c835c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993655"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="e149e-102">Metodo ICorDebugVariableHome::GetLocationType</span><span class="sxs-lookup"><span data-stu-id="e149e-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="e149e-103">Ottiene il tipo di percorso nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="e149e-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e149e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e149e-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e149e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e149e-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="e149e-106">[out] Puntatore al tipo di percorso nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="e149e-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="e149e-107">Vedere le [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumerazione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="e149e-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e149e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e149e-108">Requirements</span></span>  
 <span data-ttu-id="e149e-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e149e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e149e-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e149e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e149e-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e149e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e149e-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e149e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e149e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e149e-113">See also</span></span>

- [<span data-ttu-id="e149e-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e149e-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="e149e-115">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="e149e-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
