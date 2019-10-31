---
title: Metodo ICorDebugArrayValue::GetElementType
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
ms.openlocfilehash: d4de3405f84bfc08f7e1519bc7f9604eb1f5a14e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088295"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="3baad-102">Metodo ICorDebugArrayValue::GetElementType</span><span class="sxs-lookup"><span data-stu-id="3baad-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="3baad-103">Ottiene un valore che indica il tipo semplice degli elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="3baad-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3baad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3baad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3baad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3baad-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="3baad-106">out Puntatore a un valore dell'enumerazione CorElementType che indica il tipo.</span><span class="sxs-lookup"><span data-stu-id="3baad-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3baad-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3baad-107">Requirements</span></span>  
 <span data-ttu-id="3baad-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3baad-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3baad-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3baad-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3baad-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3baad-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3baad-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3baad-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
