---
title: Metodo ICorDebugVariableHome::GetLocationType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ec44705f75959dce893932789b026504d65a3105
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="9188f-102">Metodo ICorDebugVariableHome::GetLocationType</span><span class="sxs-lookup"><span data-stu-id="9188f-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="9188f-103">Ottiene il tipo di posizione nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="9188f-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9188f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9188f-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9188f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9188f-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="9188f-106">[out] Puntatore al tipo di percorso nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="9188f-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="9188f-107">Vedere il [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumerazione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="9188f-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9188f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9188f-108">Requirements</span></span>  
 <span data-ttu-id="9188f-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9188f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9188f-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9188f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9188f-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9188f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9188f-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9188f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9188f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9188f-113">See Also</span></span>  
 [<span data-ttu-id="9188f-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="9188f-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="9188f-115">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="9188f-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
