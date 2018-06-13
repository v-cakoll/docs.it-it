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
ms.openlocfilehash: c04fa944f2a3da9b6548ada36443d5dda4725f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421129"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="a347d-102">Metodo ICorDebugVariableHome::GetLocationType</span><span class="sxs-lookup"><span data-stu-id="a347d-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="a347d-103">Ottiene il tipo di posizione nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="a347d-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a347d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a347d-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a347d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a347d-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="a347d-106">[out] Puntatore al tipo di percorso nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="a347d-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="a347d-107">Vedere il [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumerazione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="a347d-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a347d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a347d-108">Requirements</span></span>  
 <span data-ttu-id="a347d-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a347d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a347d-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a347d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a347d-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a347d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a347d-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a347d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a347d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a347d-113">See Also</span></span>  
 [<span data-ttu-id="a347d-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a347d-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="a347d-115">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="a347d-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
