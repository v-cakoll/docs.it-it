---
title: Metodo ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c488ca3a77f2c2b2a40c6143989cd86adf071787
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737438"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="b7fee-102">Metodo ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="b7fee-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="b7fee-103">Ottiene un valore che indica se tutte le dimensioni di questa matrice dispone di un indice di base di diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="b7fee-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7fee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7fee-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7fee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7fee-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="b7fee-106">[out] Un puntatore a un valore booleano che è `true` se una o più dimensioni di questo `ICorDebugArrayValue` oggetto dispone di un indice di base di diverso da zero; in caso contrario, il valore booleano è `false`.</span><span class="sxs-lookup"><span data-stu-id="b7fee-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7fee-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7fee-107">Requirements</span></span>  
 <span data-ttu-id="b7fee-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7fee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7fee-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7fee-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7fee-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7fee-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7fee-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7fee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
