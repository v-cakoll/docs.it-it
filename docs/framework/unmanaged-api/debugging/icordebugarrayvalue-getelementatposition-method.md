---
title: Metodo ICorDebugArrayValue::GetElementAtPosition
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c26a55815e57126895902275148940c5271c235b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="16d44-102">Metodo ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="16d44-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="16d44-103">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="16d44-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16d44-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16d44-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16d44-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="16d44-106">[in] La posizione dell'elemento da recuperare.</span><span class="sxs-lookup"><span data-stu-id="16d44-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="16d44-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="16d44-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d44-108">Note</span><span class="sxs-lookup"><span data-stu-id="16d44-108">Remarks</span></span>  
 <span data-ttu-id="16d44-109">Il layout di una matrice multidimensionale segue lo stile C++ layout della matrice.</span><span class="sxs-lookup"><span data-stu-id="16d44-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d44-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16d44-110">Requirements</span></span>  
 <span data-ttu-id="16d44-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16d44-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d44-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="16d44-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16d44-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16d44-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16d44-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16d44-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
