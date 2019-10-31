---
title: Metodo ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 7f3010cccc584288608b3f6ba95efbeb95f271fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132051"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="cce91-102">Metodo ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="cce91-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="cce91-103">Ottiene un valore CorElementType che descrive il tipo nativo del Common Language Runtime (CLR) <xref:System.Type> rappresentato da ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="cce91-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cce91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cce91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cce91-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="cce91-106">out Puntatore a un valore dell'enumerazione `CorElementType` che indica la <xref:System.Type> CLR rappresentata da questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cce91-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cce91-107">Note</span><span class="sxs-lookup"><span data-stu-id="cce91-107">Remarks</span></span>  
 <span data-ttu-id="cce91-108">Se il valore di `ty` è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, è possibile chiamare il metodo [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico. in caso contrario, non chiamare `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="cce91-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cce91-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cce91-109">Requirements</span></span>  
 <span data-ttu-id="cce91-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cce91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cce91-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cce91-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cce91-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cce91-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cce91-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cce91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
