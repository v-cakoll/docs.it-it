---
title: Metodo ICorDebugReferenceValue::IsNull
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: e8b778c0880040f5ffd639a445fd5663ce493219
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379091"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="e2d9b-102">Metodo ICorDebugReferenceValue::IsNull</span><span class="sxs-lookup"><span data-stu-id="e2d9b-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="e2d9b-103">Ottiene un valore che indica se questo ICorDebugReferenceValue è un valore null, nel qual caso `ICorDebugReferenceValue` non fa riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2d9b-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2d9b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2d9b-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="e2d9b-106">out Puntatore a un valore booleano che è `true` se l' `ICorDebugReferenceValue` oggetto è null; in caso contrario, `pbNull` è `false` .</span><span class="sxs-lookup"><span data-stu-id="e2d9b-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d9b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2d9b-107">Requirements</span></span>  
 <span data-ttu-id="e2d9b-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d9b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d9b-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2d9b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2d9b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d9b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d9b-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d9b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
