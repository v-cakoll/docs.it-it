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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed37e6eae3ec4f6e69215be6a42afe7fe86ff393
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768663"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="5a4ea-102">Metodo ICorDebugReferenceValue::IsNull</span><span class="sxs-lookup"><span data-stu-id="5a4ea-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="5a4ea-103">Ottiene un valore che indica se l'interfaccia ICorDebugReferenceValue è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5a4ea-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a4ea-104">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a4ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a4ea-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="5a4ea-106">[out] Un puntatore a un valore booleano che è `true` se l'oggetto `ICorDebugReferenceValue` oggetto è null; in caso contrario, `pbNull` è `false`.</span><span class="sxs-lookup"><span data-stu-id="5a4ea-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4ea-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a4ea-107">Requirements</span></span>  
 <span data-ttu-id="5a4ea-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4ea-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a4ea-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a4ea-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a4ea-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a4ea-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
