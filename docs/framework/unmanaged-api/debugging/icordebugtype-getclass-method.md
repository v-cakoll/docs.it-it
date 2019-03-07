---
title: Metodo ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0915027ce6a3768ff854eafc5496c5057081cc4d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499537"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="7f5e9-102">Metodo ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="7f5e9-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="7f5e9-103">Ottiene un puntatore a interfaccia ICorDebugClass che rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="7f5e9-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f5e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f5e9-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f5e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f5e9-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="7f5e9-106">[out] Un puntatore all'indirizzo di un `ICorDebugClass` interfaccia che rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="7f5e9-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f5e9-107">Note</span><span class="sxs-lookup"><span data-stu-id="7f5e9-107">Remarks</span></span>  
 <span data-ttu-id="7f5e9-108">`GetClass` può essere chiamato solo in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="7f5e9-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="7f5e9-109">Chiamare [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) prima di chiamare `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="7f5e9-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="7f5e9-110">Se `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, CorElementType `GetClass` può essere chiamato per ottenere il tipo privo di istanze per un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="7f5e9-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f5e9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f5e9-111">Requirements</span></span>  
 <span data-ttu-id="7f5e9-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f5e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f5e9-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f5e9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f5e9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f5e9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f5e9-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f5e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
