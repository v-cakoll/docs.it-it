---
title: Metodo ICorDebugType::GetFirstTypeParameter
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3031cf2d9509f94b50c386b44e6d9e5d9ee5509c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768223"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="2904e-102">Metodo ICorDebugType::GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="2904e-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="2904e-103">Ottiene un puntatore a interfaccia ICorDebugType che rappresenta il primo <xref:System.Type> parametro del tipo rappresentato da questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="2904e-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2904e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2904e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2904e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2904e-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="2904e-106">[out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il primo parametro.</span><span class="sxs-lookup"><span data-stu-id="2904e-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2904e-107">Note</span><span class="sxs-lookup"><span data-stu-id="2904e-107">Remarks</span></span>  
 <span data-ttu-id="2904e-108">`GetFirstTypeParameter` può essere chiamato in casi in cui le informazioni aggiuntive sul tipo prevede al massimo un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="2904e-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="2904e-109">In particolare, può essere utilizzato se il tipo è un ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR, come indicato dal [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2904e-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2904e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2904e-110">Requirements</span></span>  
 <span data-ttu-id="2904e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2904e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2904e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2904e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2904e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2904e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2904e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2904e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
