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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d881a1fe3965b6e1d89e6172c887061434cd52ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418718"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="ecfe0-102">Metodo ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="ecfe0-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="ecfe0-103">Ottiene un valore CorElementType che descrive il tipo nativo di common language runtime (CLR) <xref:System.Type> rappresentato da ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="ecfe0-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfe0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecfe0-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecfe0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ecfe0-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="ecfe0-106">[out] Un puntatore a un valore di `CorElementType` enumerazione che indica il CLR <xref:System.Type> da questo `ICorDebugType` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="ecfe0-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecfe0-107">Note</span><span class="sxs-lookup"><span data-stu-id="ecfe0-107">Remarks</span></span>  
 <span data-ttu-id="ecfe0-108">Se il valore di `ty` è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, il [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) metodo può essere chiamato per ottenere il tipo privo di istanze per un tipo generico; in caso contrario, non chiamare `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="ecfe0-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecfe0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecfe0-109">Requirements</span></span>  
 <span data-ttu-id="ecfe0-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecfe0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecfe0-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ecfe0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecfe0-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ecfe0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecfe0-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecfe0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
