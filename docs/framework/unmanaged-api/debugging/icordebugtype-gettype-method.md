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
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379917"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="ef412-102">Metodo ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="ef412-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="ef412-103">Ottiene un valore CorElementType che descrive il tipo nativo del Common Language Runtime (CLR) <xref:System.Type> rappresentato da ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="ef412-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef412-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef412-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef412-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef412-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="ef412-106">out Puntatore a un valore dell' `CorElementType` enumerazione che indica il CLR rappresentato dall'oggetto <xref:System.Type> `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="ef412-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef412-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef412-107">Remarks</span></span>  
 <span data-ttu-id="ef412-108">Se il valore di `ty` è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, il metodo [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) può essere chiamato per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico. in caso contrario, non chiamare `ICorDebugType::GetClass` .</span><span class="sxs-lookup"><span data-stu-id="ef412-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef412-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef412-109">Requirements</span></span>  
 <span data-ttu-id="ef412-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef412-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef412-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef412-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef412-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef412-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef412-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef412-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
