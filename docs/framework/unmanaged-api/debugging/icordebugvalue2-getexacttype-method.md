---
title: Metodo ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 441d225dadbbca09ab27c8ccd70debe32f4c12da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140262"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="b1786-102">Metodo ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="b1786-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="b1786-103">Ottiene un puntatore a interfaccia a un oggetto "ICorDebugType" che rappresenta il <xref:System.Type> di questo valore.</span><span class="sxs-lookup"><span data-stu-id="b1786-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1786-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1786-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1786-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1786-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="b1786-106">out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la <xref:System.Type> del valore rappresentato da questo oggetto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="b1786-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1786-107">Note</span><span class="sxs-lookup"><span data-stu-id="b1786-107">Remarks</span></span>  
 <span data-ttu-id="b1786-108">Il metodo `GetExactType` in grado di riconoscere i generics sostituisce entrambi i metodi [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) e [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) , ciascuno dei quali restituisce informazioni sul tipo di un valore.</span><span class="sxs-lookup"><span data-stu-id="b1786-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1786-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1786-109">Requirements</span></span>  
 <span data-ttu-id="b1786-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1786-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1786-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1786-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1786-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1786-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1786-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1786-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1786-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1786-114">See also</span></span>
